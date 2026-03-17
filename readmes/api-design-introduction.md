# API Design

## Introduction
Application Design Interface (API) design is the `process` of defining the `interface` between different software `components`.
This involves specifying the `endpoints`, `request/response` formats, and the `operations` performed on the API.
Examples of APIs are `RESTful API` and `GraphQL`.

## REST API
A `REST API` is a set of rules that developers follow when creating APIs. It relies on standard `HTTP` methods and uses `resource-based` URLs to perform operations and has these principles:

| Principle                   | Explanation                                                                                                                          |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| Statelessness               | Each `request` from a client must contain all information needed for processing, and the server does not store any session data.     |
| Uniform Interface           | Resources are accessed in a consistent manner, typically via URIs (Uniform Resource Identifiers).                                    |
| Resource-based Architecture | Everything is considered a resource (e.g.; users, posts, comments), and these resources are manipulated using standard HTTP methods. |

Please click [here](https://github.com/shumarb/learning/blob/main/readmes/rest-apis.md) for more information on REST APIs.

## Best Practices
| Practice                      | Good Example                                 | Bad Example                                                                      |
|-------------------------------|----------------------------------------------|----------------------------------------------------------------------------------|
| Use Verbs                     | GET/books                                    | Get /getAllBooks                                                                 |
| Use appropriate HTTP Methods  | PUT /books/123                               | POST /books/123/update                                                           |
| Use Proper Status Codes       | 200 OK for successful GET, POST, PUT, DELETE | 200 OK for all responses                                                         |
| Consistent Naming Conventions | Using plural nouns (/books/123, /authors)    | Mixing singlular & plural nouns (/book/123, /authors)                            |
| Implement Pagination          | Using query parameters (?page=2&limit=50)    | Returning all records in a single response, which is slow and resource-intensive |
