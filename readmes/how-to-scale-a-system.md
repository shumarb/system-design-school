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
- Scale up via using more powerful machines (e.g.: Cloud Computing).

### Horizontal Scaling
- Scaling via running multiples instances of `stateless` services.
- Stateless nature enables seamless distribution of requests across instances using load balancers.

### Partitioning
- Split requests and data into `shards` and distribute them across `services`/`databases`,
- E.g.: Partition data based on user ID.
- Implement `consistent hashing` to ensure balanced partitioning.

### Caching
- Improve query read performance and reduce database load by storing frequently-accessed data in faster memory storage (e.g.: in-memory caches, Redis, Memcached).
