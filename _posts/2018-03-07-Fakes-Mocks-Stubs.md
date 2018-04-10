---
layout: post
title:  "Test Doubles: Fakes, Mocks, Stubs"
date:   2018-03-07 12:42:01 +1100
categories: [definitions,Testing]
tags:  [definitions,Testing]
---
# Test Doubles
A test double is a generic term that encompass various methods which can be used to replace production objects/functions to isolate items under test from the implementation of their dependencies. The use of test doubles is often facilitated by dependency inversion. Test doubles also provide a means of keeping tests fast by removing slow running dependencies (generally IO) like databases, web servers and file systems.

Examples of test doubles are:
* Stubs
* Spies
* Mocks
* Dummies
* Fakes

## Explanations and examples of test doubles
### Stubs
Stubs return hard coded values and the result returned doesn't change for different inputs. They provide a method of ensuring that the returned value is always the same.

The following example in Java shows how a usually fluctuating stock price has been stubbed out for testing purposes.

Code:
```Java
public interface StockFeed {
    int getSharePrice(String company);
}

public class StockAnalyzer {
    private StockFeed stockFeed;

    public StockAnalyzer(StockFeed feed) {
        stockFeed = feed;
    }

    public int getMyobPrice() {
        return stockFeed.getSharePrice("MYOB");
    }
}
```

And the tests where the interface `StockFeed` has been stubbed:
```Java
public class StubExampleTest extends TestCase {
    @Test
    public void testStockAnalyzerReturnsStockPrice() {
        StockFeed stubStockFeed = new StubStockFeed();
        StockAnalyzer itemUnderTest = new StockAnalyzer(stubStockFeed);

        assertEquals(100, itemUnderTest.getMyobPrice());
    }
}

class StubStockFeed implements StockFeed {
    @Override
    public int getSharePrice(String company) {
        return 100;
    }
}
```

In summary a stub implementation attempts to have functional parity of the called component often by returning static data.

### Spies
Spies provided a way of "listening" to some method to see if it was called and how many times, they can also record more information on how they were called including how many arguments and what values they contained.

Using the same code example above we can use a spy to ensure that the `getSharePrice` method was called in the `StockAnalyzer`:
```Java
public class SpyExampleTest extends TestCase {
    @Test
    public void testStockAnalyzerReturnsStockPrice() {
        SpyStockFeed spyStockFeed = new SpyStockFeed(); // In the test use the specific implementation and not the refer to the interface.
        StockAnalyzer itemUnderTest = new StockAnalyzer(spyStockFeed);

        int stockPrice = itemUnderTest.getMyobPrice();

        assertEquals(1, spyStockFeed.getSharePriceCallCount());
    }
}

class SpyStockFeed implements StockFeed {
    // Note implements the StockFeed interface, but has public method acting as the Spy. This is not part of the StockFeed interface.
    private int sharePriceCallCount = 0;

    public int getSharePriceCallCount() {
        return sharePriceCallCount;
    }

    @Override
    public int getSharePrice(String company) {
        sharePriceCallCount++;
        return 100;
    }
}
```

### Mocks
Mocks are the more intricate of the test double types and the term Mock is often used in the general sense for all types of test doubles. They provide a method of verifying behavior, they do this by pre-programming objects with expectations which form a specification of calls they are expected to receive (Martin Fowler). 

In this test the return value isn't important, rather the test is asserting that the `StockFeed` has it's `getSharePrice` method called and that it was called with the value "MYOB" by the behavior of the `getMyobPrice`

```Java
public class MockExampleTest extends TestCase {
    @Test
    public void testStockAnalyzerGetsStockPriceForCompany() {
        MockStockFeed mockStockFeed = new MockStockFeed();
        StockAnalyzer itemUnderTest = new StockAnalyzer(mockStockFeed);

        itemUnderTest.getMyobPrice();

        assertTrue(mockStockFeed.getSharePriceWasCalled());
        assertEquals("MYOB", mockStockFeed.getCompanyCalled());
    }
}

class MockStockFeed implements StockFeed {
    private String companyCalled = "";
    private Boolean getSharePriceWasCalled = false;

    public Boolean getSharePriceWasCalled() {
        return getSharePriceWasCalled;
    }

    public String getCompanyCalled() {
        return companyCalled;
    }

    @Override
    public int getSharePrice(String company) {
        getSharePriceWasCalled = true;
        companyCalled = company;
        
        return 100;
    }
}
```

In summary a mock is an implementation of the contract, when used by mocking frameworks is generally implemented as a “spy” (see above

### Dummies
Dummy objects contain no logic and return no values. They are used only to fill parameter lists and are never actually used. Dummies can also indicate a design problem and can be akin to "null" being an acceptable method parameter.

A slightly different example showing the test only where a dummy authorizer has been used in place of a real object.

```Java
public interface Authorizer {
    void authorize(String username, String password);
}

class System {
    private Authorizer authorizer;
    private int loginCount = 0;

    public System(Authorizer authorizer){
        this.authorizer = authorizer;
    }
    
    public int getLoginCount() {
        return loginCount;        
    }
}
```

In the test a dummy `Authorizer` is used.

```Java
public class DummyExampleTests extends TestCase {
    @Test
    public void testNewSystemHasNoLoggedInUsers() {
        Authorizer dummyAuthorizer = new DummyAuthorizer();
        System itemUnderTest = new System(dummyAuthorizer);

        assertEquals(0, itemUnderTest.getLoginCount());
    }
}

class DummyAuthorizer implements Authorizer {
    @Override
    public void authorize(String username, String password) {
    }
}

```

## Fakes
Fakes are objects with actual working implementations, however the implementation is usually not suitable for production and are light-weight.

Martin Fowler uses the example of an [InMemoryTestDatabase](https://martinfowler.com/bliki/InMemoryTestDatabase.html) 

## Libraries/Frameworks
Various libraries and frameworks are available that provide a more stream-lined way to setup a test double. They usually provide the capabilities of all the above varieties. Although these libraries can be handy they often make the process too easy and can encourage bad practice and mask potential code smells.

One example of this is using a mocking library to reduce the setup code for tests. Kent Beck suggests that a large amount of setup code and duplicated setup code is a good sign that your objects are too large and have too many responsibilities, this isn't as visible when using a mocking library/framework.

A list of popular mocking frameworks:
- **Java** - [mockito](http://site.mockito.org/)
- **C#** - [Moq](https://github.com/moq/moq4)
- **JavaScript** - [Sinon](http://sinonjs.org/)

## References
[TestDouble - Martin Fowler](https://martinfowler.com/bliki/TestDouble.html)  
[Test Driven Development: By Example - Kent Beck](https://www.goodreads.com/book/show/387190.Test_Driven_Development)  
[Test Double Examples in Ruby](https://github.com/octopusinvitro/zagakus/blob/master/test-doubles.md)  