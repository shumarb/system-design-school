# Interview Template

## Overview
This section explains the typical interview process below the staff level at medium to large-sized companies, listed sequentially below:

| Step                                                                                                                                                                   |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Clarify Requirements](https://github.com/shumarb/system-design-school/blob/main/readmes/interview-template.md#clarify-requirements)                                   |
| [Resource Estimation](https://github.com/shumarb/system-design-school/blob/main/readmes/interview-template.md#resource-estimation)                                     |
| [Core Entities and API Endpoint Design](https://github.com/shumarb/system-design-school/blob/main/readmes/interview-template.md#core-entities-and-api-endpoint-design) |
| [High-level Design Diagram](https://github.com/shumarb/system-design-school/blob/main/readmes/interview-template.md#high-level-design-diagram)                         |

## Steps
### Clarify Requirements
Functional:
- Which features are already covered by the existing services/APIs?
- Which features need to be built?

Non-Functional:
- Core:
  - `S`calability: Design the system to be able to handle the target number of users.
  - `A`vailabilty: Design the system to be operational when needed via techniques like `replication` to avoid downtime.
  - `L`atency: Identify the acceptable latency for the system.
  - `E`fficiency: Minimize redundant operations and optimize resource usage.
  - `R`eliability: Ensure the service consistently returns correct and expected results.
  - `C`onsistency: Address data consistency between services, ensure reading from different sources generates same result, and decide data storage location.

- Special
  - Consider GDPR compliance and other privacy requirements depending on the data being stored and processed (e.g.: email).

### Resource Estimation
- Optional step.
- Important for infrastructure design questions (e.g.: Design a Rate Limiter).
- Ask:
  - How many daily users does the system need to support?
  - How long should the data be stored?
- Estimate:
  - QPS (Queries per second):
    - Read.
    - Write.
  - Ongoing connections (if applicable; e.g.: Websocket-based applications like WhatsApp).
  - Throughput (in GB/s, needed for video streaming/image-hosting problems).
  - Storage requirements based on data retention and object byte sizing using the number of strings.
  - Identify potential bottlenecks in the system (e.g.: QPS limitations).

### Core Entities and API Endpoint Design
- `Core Entities` are core domain models required to implement the functional requirements. Its naming style is the `nouns` of the functional requirements (Example: In a social media platform, the core entities are `users`, `likes`, `posts`).
- `APIs` establish a contract between the `service` and the `end user`. Hence, `REST APIs` are specified to create a `request & response interface`.
- If the system necessitates bidirectional communication, discuss technologies that facilitate this, such as `Web Sockets`, or server-to-client protocols (e.g.: Server-Sent Events).
tion, don't forget to discuss technologies that facilitate this, such as WebSockets, or server-to-client messaging protocols like Server-Sent Events.

### High-level Design Diagram
- Draw a high-level system design that includes:
  - Main components of the system and how they interact with each other.
  - Data flow: How data moves through the system.
  - Traffic pattern (if relevant to problem): Show how the system handles different types of traffic (e.g.: push vs pull for Twitter).
  - Database model/schema, and which fields to index if required.
- Ensure design diagram covers every feature in the functional requirements.
- Focus on key components that are specific to unique problems the system is solving, and don't delve into particulars of specific technologies or use buzzwords.
