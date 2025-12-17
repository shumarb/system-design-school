# Requirements

## Overview
A system has to fulfill `functional` & `non-functional` requirements.

### Functional Requirements
Functional requirements are `features` & `capabilities` that a system must have to fulfill its intended purpose.
It describes what a system is supposed to do and are focused on the specific functionalities a system should perform.
It is gathered from user needs, business objectives, or system specifications, and documented to developers and stakeholders via formates such as project requirement docs (PRDs).
Examples:
- User actions: Describing the actions a user can perform within the system (eg: creating an account, submission of documents).
- Data input & processing: Defining how the system should process, manipulate, or transform data based on user input or other sources.

### Non-functional Requirements
Non-functional requirements are the system's capability on:
- Scalability: Handling increasing amounts of work or users without compromising performance. This involves designing for `horizontal & vertical scaling`, `optimizing` resource usage, and `planning` for future growth.
- Availability: A system's ability to continue functioning even in the face of failures (e.g.: hardware or network issues). This requires designing for `redundancy`, `failover mechanisms`, and `monitoring` the system's health.
- Performance: This comprises `latency` (time taken to respond to requests), and `throughput` (amount of work or transactions the system handles in a given time).
- Reliability: The services returns correct results.
- Consistency: Data is consistent between services.
- Efficiency: The service should have minimal redundant operations.