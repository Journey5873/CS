# HTTP Protocol

HTTP (HyperText Transfer Protocol) is a communication protocol used for exchanging data on the web. It operates on a client-server model which means clients send requests, and servers respond to those requests. 

It is an application layer protocol that runs on top of other layers in the network [protocol](https://www.cloudflare.com/learning/network-layer/what-is-a-protocol/) stack. Clients request resources using HTTP, and these requests are transmitted to the server through the TCP/IP protocol. The server then responds using HTTP, and the response, transmitted through the TCP/IP protocol, reaches the client.

## Request

: Client to Server

An HTTP request is the way Internet communications platforms such as web browsers ask for the information they need to load a website.

A typical HTTP request contains:

1. HTTP version type
2. a URL 
    
    It is a protocol used to indicate the location of resources on a computer network.
    
3. an HTTP method
    - **GET**: Retrieve data.
    - **PUT**: Replace a resource or create it if it doesn't exist.
    - **PATCH**: Apply partial modifications to a resource.
    - **POST**: Submit data to be processed, often used to create or update a resource.
    - **DELETE**: Request the removal of a resource.
4. HTTP request headers
    
    These headers convey core information, such as what browser the client is using and what data is being requested.
    
5. Optional HTTP body.
    
    The body of an HTTP request contains any information being submitted to the web server
    

## Response

: Server to Client

An HTTP response is what web clients (often browsers) receive from an Internet server in answer to an HTTP request.

A typical HTTP response contains:

1. an HTTP status code
    - **1xx Informational**: Request received, continuing process.
    - **2xx Success**: Request successfully received, understood, and accepted.
    - **3xx Redirection**: Further action needed to complete the request.
    - **4xx Client Error**: Client-related errors; the client seems to have made an error.
    - **5xx Server Error**: Server failed to fulfill a valid request.
2. HTTP response headers
    
    Response headers convey important information such as the language and format of the data being sent in the response body.
    
3. optional HTTP body
    
    Successful HTTP responses requests generally have a body which contains the requested information.
