Date: 2025-10-07
Tags: [[architecture]], [[network pattern]]

Push
![[Pasted image 20251007160736.png]]
Pros:
- Realtime
Cons:
- Server complexity
- Maintaining many open connections could be heavy
Examples: Websocket, gRCP, RabbitMQ

Pull
![[Pasted image 20251007160739.png]]
Pros:
- Simpler and communication is under control
Cons:
- Client complexity
- Latency is higher
Examples: SQS, Kafka, Prometheus
Related to: [[Long Pooling vs Short Pooling]]