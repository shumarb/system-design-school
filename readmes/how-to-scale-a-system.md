# How to Scale a System

## Overview
Scalability is a critical aspect of satisfying the system's non-functional requirements.

This can be achieved via:

| Technique                                                                                                                           |
|-------------------------------------------------------------------------------------------------------------------------------------|
| [Decomposition](https://github.com/shumarb/system-design-school/blob/main/readmes/how-to-scale-a-system.md#decomposition)           |
| [Vertical Scaling](https://github.com/shumarb/system-design-school/blob/main/readmes/how-to-scale-a-system.md#vertical-scaling)     |
| [Horizontal Scaling](https://github.com/shumarb/system-design-school/blob/main/readmes/how-to-scale-a-system.md#horizontal-scaling) |
| [Partitioning](https://github.com/shumarb/system-design-school/blob/main/readmes/how-to-scale-a-system.md#partitioning)             |
| [Caching](https://github.com/shumarb/system-design-school/blob/main/readmes/how-to-scale-a-system.md#caching)                       |

## Technique
### Decomposition
- Break down requirements into `microservices`, which are smaller, independent services based on specific business capabilities/requirements.
- Each microservice should focuses on a single responsibility to enhance scalability and maintainability.

### Vertical Scaling
- Increasing the capacity of a single machine by adding more resources (e.g.: CPU, Memory, etc.) rather than adding more instances of a service.

### Horizontal Scaling
- Scaling via running multiples instances of `stateless` services.
- Stateless nature enables seamless distribution of requests across instances using load balancers.

### Partitioning
- Split requests and data into `shards` and distribute them across `services`/`databases`,
- E.g.: Partition data based on user ID.
- Implement `consistent hashing` to ensure balanced partitioning.

### Caching
- Improve query read performance and reduce database load by storing frequently-accessed data in faster memory storage (e.g.: in-memory caches, Redis, Memcached).

## Buffer with Message Queues
- High-concurrency scenarios often encounter write-intensive operations.
- Frequent database writes can overload system due to disk I/O bottlenecks.
- Message queues buffer write requests, changing synchronous operations into asynchronous ones to ensure database write requests levels are manageable and prevent system crashes.

## Separating Read and Write
- Whether a system is read-heavy or write-heavy depends on the business requirements.
- `Leader-Follower` architecture: Writes occur on the `leader`, and `followers` provide `read replicas`.
- Command Query Responsibility Segregation (CQRS)
  - `Command` side (`write` side): Handles all `write` operations (`create`, `update`, `delete`) using a data model optimized for writes.
  - `Query` side (`read` side): Handles all `read` operations using a denormalized data model optimized for `reads`.
  - Changes from the `command` side are `asynchronously` propagated to the `query` side.

## Combining Techniques
- Effective scaling usually requires a multi-faceted approach using several techniques via these steps.
- `Break` down monolithic services for independent scaling
- `Partition` and `Cache` work together to distribute load efficiently while enhancing performance
- Implement `Leader-Replica` setups to enforce `Read/Write` separation for fast reads and reliable writes
- Adjust business logic to help design strategies that mitigate operational bottlenecks without compromising user experience.

## Adapting to Changing Business Requirements
- Identify practical ways of way of handling large traffic loads to drive predictable traffic patterns and enable better resource allocation.
- Example: In a weekly sales event, instead of running all sales simultaneously for all users, the load can be distributed by allocating specific days for different product categories for specific regions. (E.g: Electronics for Day 1, Clothing for Day 2).
