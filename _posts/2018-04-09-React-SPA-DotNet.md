---
layout: post
title:  "React Single Page App with ASP"
date:   2018-04-09 09:00:01 +1100
tags: ["react","ASP"]
---

# React Single Page App
The following is a short tutorial on how to create a React Single Page app using dotnet core and ASP. This will work without the need of installing Mono and will be IDE agnostic.

## Requirements
* [DotNet core SDK](https://www.microsoft.com/net/download/) 
* [Node](https://nodejs.org/en/) Required for transpiling react and packing using WebPack 

## Steps
1. Create a new folder and a new dotnet solution
```bash
mkdir ReactExample
cd ReactExample
dotnet new sln
```

2. Install the Single Page templates for dotnet core and create a new React Spa template
```bash
dotnet new --install Microsoft.AspNetCore.SpaTemplates
dotnet new react -o ReactJsSpa
```

3. Initialise the app and run it
```bash
dotnet sln add ReactJsSpa/ReactJsSpa.csproj
cd ReactJsSpa
npm install
dotnet run
```

You should now be able to access the single page app by navigating to http://localhost:5000 in your browser!
The Single Page App consists of the following components:
* ASP.NET Core and C#
* React and TypeScript for client-side code
* Webpack for building and bundling, this includes the transpiling of the react components into JS ES5 so they can be supported by most browsers  
* Bootstrap for layout and styling

The directory structure of the created app is as follows:
* **ClientApp** - Contains all of the typescript/css that makes up the single page application
    * boot.tsx - The main bootstrap of the React application, loads all of the required modules and static files (such as css). After the app is loaded it renders the app to the page and then invokes hot module replacement capabilities which allows for faster development
    * routes.tsx - Set's up all of the routes for the React SPA, for the including example this includes the counter and fetchdata routers as well as the root route
    * components - The react components of the SPA in typescript
    * css - css static resources for the spa
* **Controllers** - Contains the controllers for the server side component of the application in c#
    * HomeController - serves the React SPA
    * SampleDataController - serves the data that is supplied to the FetchData example from the SPA. 
* **Views** - The ASP views
    * Home - contains the cshtml page that is displayed while the JS is loaded and the application begins in the browsers
    * Errors - Contains the base layout template and main error page shown when the application encounters an error
The remaining files include the configurations for each of the used components
    - appsettings - ASP's setting files
    - npm-shrinkwrap - version for the npm build process
    - package.json - nuget package settings
    - tsconfig - TyeeScript settings
    - webpack - Configuration for the webpack process, everything that webpack requries to build the SPA including roots, routes, language configuration (typescript is used for the react components) etc
    - Startup.cs - this is the bootstrapping process for the ASP server side component itself. This includes the setup and routes for the MVC side

## Conclusion
That's it! in the next pos I will explain how to create an app that relies more on the ASP side of things to act as a backend as well as use ReactJS to do the transpiling of the react components instead of node.