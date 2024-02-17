# REST API


## What is API?

APIs (Application Programming Interface) are mechanisms that enable two software to communicate with each other using set of definitions and protocols.

---

## What is REST?

Representational State Transfer (REST) is a software architecture for providing standards between computer systems on the web, making it easier for systems to communicate with each other.

- REST is an architectural style that leverages the benefits of the web by utilizing the HTTP protocol.
- It serves as a communication method between clients and servers on a network.

1. **URI (Uniform Resource Identifier):** All resources (data or services) should have a unique identifier known as a URI. This allows clients to find and access resources.
2. **Utilization of HTTP Methods:** Various methods of the HTTP protocol (GET, POST, PUT, DELETE, etc.) are used to perform specific actions on resources. 
3. **Representation:** Resources can have multiple representations, and clients and servers exchange information through these representations. Common formats include JSON or XML.

In the REST architecture, resources are represented by Uniform Resource Identifiers (URIs), and their actions are indicated using HTTP methods, primarily GET, POST, PUT, DELETE, and others.

### Principles of the REST

REST uses HTTP protocols so it leverages existing infra on web.

1. **Statelessness**
    - The server doesn’t need to know anything about what state the client is in.
    - Statelessness refers to a communication method in which the server completes every client request independently of all previous requests.
2. **Cacheability**
    - RESTful web services support caching, which can improve performance by reducing the need for redundant requests.

---

## What is REST API?

Service API implemented based on REST. 

### REST API Design Basic Rules

1. URIs should represent the resources.
2. Actions on resources should be expressed with HTTP methods (GET, PUT, POST, DELETE, etc.).

[Reference]

[What is REST? | Codecademy](https://www.codecademy.com/article/what-is-rest)

[What is RESTful API? - RESTful API Explained - AWS](https://aws.amazon.com/what-is/restful-api/?nc1=h_ls)

[[간단정리] REST, REST API, RESTful 특징](https://hahahoho5915.tistory.com/54)
