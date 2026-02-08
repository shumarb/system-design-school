# Core Challenges

## Overview
Common challenges that systems face sem from serving a large scale of users by adding more machines.

| Challenges                                                                                                                                                                |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Too Many Concurrent Users](https://github.com/shumarb/system-design-school/blob/main/readmes/core-challenges.md#too-many-concurrent-users)                               |
| [Too Much Data to Move Around](https://github.com/shumarb/system-design-school/blob/main/readmes/core-challenges.md#too-much-data-to-move-around)                         |
| [The System should be Fast and Responsive](https://github.com/shumarb/system-design-school/blob/main/readmes/core-challenges.md#the-system-should-be-fast-and-responsive) |
| [Inconsistent (Outdated) States](https://github.com/shumarb/system-design-school/blob/main/readmes/core-challenges.md#inconsistent-outdated-states)                       |

## Challenges
### Too Many Concurrent Users
- A single machine/database has an RPS/QPS limits. The server's performance degenerates fast once this limit is exceeded.
- Solution: `Repetition`, where same assets of the application are repeated, and users are randomly assigned to each replication.
    - When the replicated assets are `server` logic, it is called `Load Balancing`.
    - When the replicated assets are `data`, it is called `Database Replicas`.

## Too Much Data to Move Around
- Data becomes `big` when it is no longer possible to hold everything in one machine (e.g.: All movies on Netflix).
- Solution: `Sharding`, where the data is partitioned by some logic.

## The System should be Fast and Responsive
- Most user-facing applications must be quick (e.g.: response times exceeding 1-second results in poor user experience).
- Most typical writing processes involve many data queries and updates, hence they last far longer than the 1-second limit.
- Solution: `Asynchrony` (e.g.: Message Queue like Kafka)
  - While processing continues in the back end, the write request is returned immediately after the server receives its data and puts the data in the queue.
  - After receiving the response from the server, the client-side logic has sufficient room (1-2 seconds) for a speedy user experience (e.g.: Showing some UI before redirecting the user to read the result).

## Inconsistent (Outdated) States
- This is a result of solving the challenges `Too Many Concurrent Users` and `The System should be Fast and Responsive`.
- With data `replication` and `asynchronous` data update, the read requests can easily see inconsistent data (old versions or deleted data).
- Solution: `Eventual Consistency`
  - Because the outdated read resulted from replication and asynchronous updates will eventually disappear when the servers catch up, we build the user experience so that seeing outdated data for a short time period is acceptable.
  - Most applications tolerate `eventual consistency` well, because the alternative is losing data forever or being very slow.
  - There are exceptions: banking or payment-related applications, where any inconsistency is unacceptable, so the applications must wait for all processing to finish before returning anything to the users, causing the applications to run slower compared to non-baking applications.