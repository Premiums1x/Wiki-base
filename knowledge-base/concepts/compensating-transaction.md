---
concept: compensating-transaction
entity_type: technique
aliases: []
sources: ["raw\\03-frontend-development\\async_task_queue_case_study.md"]
confidence: high
created_at: 2026-06-26T06:19:24Z
---

## Definition
A Compensating Transaction is a business transaction that includes a series of steps to ensure that the effects of a previously completed transaction can be undone or rolled back, in case the transaction fails in some step. This concept extends the basic principles of financial transactions where every transaction needs a counterpart operation in case of failure. In computer science and distributed systems, it builds on the concept of two-phase-commit to ensure data consistency across multiple participants.

## How it works
In a Compensating Transaction mechanism, each step in a business process includes a compensating step—a process that is executed to reverse the effects of the original step. The idea is that if an earlier step in the transaction causes an error, the subsequent compensating transactions are executed to compensate or undo the effect of the previous steps, thereby rolling back the overall transaction to a consistent state.

For example, in a distributed system where multiple services participate in a single business transaction, such as an order placement workflow (placing an order, charging the customer, reserving inventory), if any step in the process fails, each successful step before the failure is compensated for, reverting the system to a previous state as if the transaction had never begun.

### Variants
- **Two-Phase Commit (2PC)**: This method is a more general concept related to ensuring atomicity in distributed transactions. It depends on two-phase-commit for coordinating all participants in a transaction such that they all commit or all abort. However, 2PC alone does not necessarily handle failure recovery; it needs a compensating transaction approach to handle scenarios where a participant fails after committing.

- **Sagas**: Sagas are a pattern composed of long-running activities and compensating transactions that can rollback the work done in a series of synchronous or asynchronous steps. Sagas are a specific implementation that optimizes the handling of long-running business processes by automatically scheduling and executing compensating actions if any step fails.

- **Chained Compensations**: In these implementations, the compensating transactions are chained in reverse order of commitment. If transaction A is committed, then transaction B, and B fails, the system will attempt to compensate B first, then if needed, A.

## Trade-offs
Compensating Transactions come with several trade-offs:

- **Complexity**: The need to design, implement, and maintain compensating actions for each transaction adds complexity and an additional layer of operational overhead.
- **Latency and Performance**: Executing compensating transactions incurs additional overhead, which can increase the latency of the overall transaction process.
- **Dependability**: Maintaining a fully consistent state often requires coordination across multiple services or nodes, which can introduce points of failure and increase the complexity of failure recovery strategies.

## See also
two-phase-commit
sagas