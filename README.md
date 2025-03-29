# Distributed-Task-Queue
Fault-tolerant distributed task queue with priority scheduling.
## Tech to use
1. Task Submission (gRPC API)
    - Expose a gRPC API for clients to submit tasks with priority levels.
    - Use Redis to temporarily store and prioritize tasks before dispatching.

2. Task Queue (RabbitMQ)
    - Use RabbitMQ with multiple priority queues or delayed queues.
    - Each worker can consume tasks based on priority.

3. Worker Nodes (Golang)
    - Implement workers that fetch tasks, process them, and handle retries.
    - Use Redis for tracking task status (e.g., pending, in-progress, failed).

4. Fault Tolerance & Retry Mechanism
    - Implement exponential backoff retry strategy.
    - Store failed tasks in a Redis dead-letter queue for further analysis.

5. Health Monitoring
    - Expose Prometheus metrics and logs for monitoring failures and queue performance.
