Date: 2026-02-03
Tags: [[network pattern]], [[architecture]]

Elastic Load Balance (ELB) is a general concept of load balancing, which has:
- Application Load Balance (ALB) balance the load at the layer 7 (HTTP, WS...)
- Network Load Balance (NLB) balance the the load at the layer 4 (TCP, UDP)

| Feature            | Application Load Balancer (ALB)     | Network Load Balancer (NLB)   |
| ------------------ | ----------------------------------- | ----------------------------- |
| **OSI Layer**      | Layer 7 (Application)               | Layer 4 (Transport)           |
| **Protocols**      | HTTP, HTTPS, gRPC, WebSocket        | TCP, TLS, UDP                 |
| **Routing**        | Content-based (Path, Host, Headers) | IP Address & Port             |
| **Use Case**       | Microservices, Web Apps             | High Performance, IoT, Gaming |
