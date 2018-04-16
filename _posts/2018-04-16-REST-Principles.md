---
layout: post
title:  "REST Principles"
date:   2018-04-16 09:00:01 +1100
tags: ["REST"]
---

# REST Principles
Recently I created a REST API for my TicTacToe game. It consisted of endpoints which allowed the creation of new games of any size between 3-10, taking turns and forfeiting the game.

## REST
REST API stands for **Re**presentational **S**tate **T**ransfer **A**pplication **P**rogramming **I**nterface. There is no official standard for REST unlike SOAP. This is because REST is more of an architectural style than a protocol. REST has been designed closely to work with the HTTP specification.

REST has been designed to keep in mind performance, scalability, simplicity, modifiability, visibility, portability and reliability.

Rest also has 6 guiding restraints which restrict the ways that the server may process and respond to client requests. These include statelessness, cacheability, layered system, code on demand, uniform interface

## HTTP Based REST
I applied REST to my TicTacToe game through HTTP. HTTP Methods apply to REST in the following way:
* **Get** provides details about the entity at the end point without changing it's state or having any side effects (use to get the current state of the game in play)
* **Put** updates the entire entity at the end point (used to make a turn in the game)
* **Patch** updates on one field at the end point
* **Post** creates a new entity at the end point (used to start a new game)
* **Delete** deletes the entity at the end point (not used in my game)

## HTTP Response Codes
HTTP response codes can also be used in relation to REST Requests
* **200: Success** usually after a GET request to indicate that the request was successful and contains a response body 
* **201: Created** usually after a POST request to indicate that the request was successful, the entity was created and contains the response body
* **204: Success** usually after a PUT request to indicate that the request was successful and contains a response body 
* **400: Bad Request** The request URI (Uniform Resource Identifier) doesn't exist
* **401: Unauthorized**
* **403: Forbidden** The request is not permitted. This can be caused by access control list failures
* **404: Not Found** The requested resource wasn't found
* **405: Method not allowed**
* **406: Not acceptable**
* **415: Unsupported media type** The endpoint does not support the format of the request body.

## Useful tools
A list of useful tools for analyzing and creating REST services:
[Postman](https://www.getpostman.com/) - for making requests and seeing their responses  
[Fiddler](https://www.telerik.com/fiddler) - analyzing network traffic on windows  
[WireShark](https://www.wireshark.org/) - analyzing network traffic on OSX  