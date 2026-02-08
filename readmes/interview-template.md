# Interview Template

## Overview
This section explains the typical interview process below the staff level at medium to large-sized companies, listed sequentially below:

## Steps
### 1. Clarify Functional Requirements
- Which features are already covered by the existing services/APIs?
- Which features need to be built?

### 2. Go through Non-Functional Requirements
Discuss with the interviewer any relevant requirements below:
- Core requirements:
  - `S`calability: Design the system to be able to handle the target number of users.
  - `A`vailabilty: Design the system to be operational when needed via techniques like `replication` to avoid downtime.
  - `L`atency: Identify the acceptable latency for the system.
  - `E`fficiency: Minimize redundant operations and optimize resource usage.
  - `R`eliability: Ensure the service consistently returns correct and expected results.
  - `C`onsistency: Address data consistency between services, ensure reading from different sources generates same result, and decide data storage location.

- Special
  - Consider GDPR compliance and other privacy requirements depending on the data being stored and processed (e.g.: email).

### 3. Resource Estimation
- This step is optional, and the interviewer may say "a lot of data/users".
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