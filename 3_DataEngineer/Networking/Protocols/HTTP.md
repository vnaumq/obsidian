 [[Protocols]]
**_Hypertext Transfer Protocol (HTTP)_** is an [application-layer](https://en.wikipedia.org/wiki/Application_Layer) protocol for transmitting hypermedia documents, such as HTML. It was designed for communication between web browsers and web servers, but it can also be used for other purposes, such as machine-to-machine communication, programmatic access to APIs, and more.

HTTP follows a classical [client-server model](https://en.wikipedia.org/wiki/Client%E2%80%93server_model), with a client opening a connection to make a request, then waiting until it receives a response from the server. HTTP is a [stateless protocol](https://en.wikipedia.org/wiki/Stateless_protocol), meaning that the server does not keep any session data between two requests, although the later addition of [cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies) adds state to some client-server interactions.

## [References](https://developer.mozilla.org/en-US/docs/Web/HTTP#references)

The HTTP reference documentation contains detailed information about headers, request methods, status responses, and lists relevant specifications and standards documents.

[HTTP headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)

Message headers are used to send metadata about a resource or a HTTP message, and to describe the behavior of the client or the server.

[HTTP request methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)

Request methods indicate the purpose of the request and what is expected if the request is successful. The most common methods are [`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) and [`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) for retrieving and sending data to servers, respectively, but there are other methods which serve different purposes.

[HTTP response status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

Response status codes indicate the outcome of a specific HTTP request. Responses are grouped in five classes: informational, successful, redirections, client errors, and server errors.

[HTTP resources and specifications](https://developer.mozilla.org/en-US/docs/Web/HTTP/Resources_and_specifications)

This page lists relevant resources about HTTP since it was first specified in the early 1990s.

![[fetching-a-page.svg]]
![[http-layers.svg]]