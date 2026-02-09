# How to Scale a System

## Overview
Scalability is a critical aspect of satisfying the system's non-functional requirements.

This can be achieved via:

| Technique                                                                                                                           |
|-------------------------------------------------------------------------------------------------------------------------------------|
| [Decomposition](https://github.com/shumarb/system-design-school/blob/main/readmes/how-to-scale-a-system.md#decomposition)           |
| [Vertical Scaling](https://github.com/shumarb/system-design-school/blob/main/readmes/how-to-scale-a-system.md#vertical-scaling)     |
| [Horizontal Scaling](https://github.com/shumarb/system-design-school/blob/main/readmes/how-to-scale-a-system.md#horizontal-scaling) |

## Technique
### Decomposition
- Break down requirements into `microservices`, which are smaller, independent services based on specific business capabilities/requirements.
- Each microservice should focuses on a single responsibility to enhance scalability and maintainability.

### Vertical Scaling
- Scale up via using more powerful machines (e.g.: Cloud Computing).

### Horizontal Scaling
- Scaling via running multiples instances of `stateless` services.
- Stateless nature enables seamless distribution of requests across instances using load balancers.