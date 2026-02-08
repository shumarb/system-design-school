# Introduction

| Topic                                                                                                                                                                                           |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Overview](https://github.com/shumarb/system-design-school/blob/main/readmes/introduction.md#overview)                                                                                          |
| [Requirements](https://github.com/shumarb/system-design-school/blob/main/readmes/introduction.md#requirements)                                                                                  |
| [Comparison to Object-Oriented Programming (OOP) Design](https://github.com/shumarb/system-design-school/blob/main/readmes/introduction.md#comparison-to-object-oriented-programming-oop-design) |

## Overview
System Design is the process of designing a complex system to meet specific `requirements` and `goals`, typically aimed at providing a service to the end user.

This involves designing these aspects in order to create a `cohesive` and `functional` system:
1. Understand the application requirements.
2. Identify the appropriate data systems to manage the diverse tasks.
3. Use application code to stitch together different `components` and `technologies` allowing them to work in harmony.

System Design focuses on these concepts:
1. Services: Components, applications, and APIs that provide specific functionality or processing capabilities. Services are created as `microservices` (`monolith`) to enable scalability, maintainability, and flexibility.
2. Dataflow: Data flow within & between services is crucial to ensure efficient `processing`, `timely communication`, and `accurate` results. This involves understanding the `data formats`, `protocols`, and `communication` pattens between `services`.
3. Storage: `Databases`, `caches`, and `file systems` required to `store` and `manage` data throughout the system. This involves selecting appropriate storage technologies, data modeling, and ensuring data `consistency` & `durability`.

## Requirements
A system must fulfill [requirements](https://github.com/shumarb/system-design-school/blob/main/readmes/requirements.md).

## Comparison to Object-Oriented Programming (OOP) Design
| Topic         | OOP Design                                              | System Design                                                            |
|---------------|---------------------------------------------------------|--------------------------------------------------------------------------|
| Example       | Design a parking lot.                                   | Design Uber.                                                             |
| Skills tested | Write well-structuted OOP code, class inheritance, etc. | Architecture, Dataflow, Scalability.                                     |
| Questions     | Write well-structuted OOP code, class inheritance, etc. | Architecture, Dataflow, Scalability, Tradeoffs, Resource Estimates, etc. |