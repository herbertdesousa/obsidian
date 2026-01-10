Date: 2025-04-08
Tags: [[scalability]], [[DDD]], [[Start Simple, Complex when you need]]

Major part of the time you will handle with domain operations which don't need performance, keeping them into *domain* folder to guarantee:
- Apart from world: they don't know the rest of world
- Testability: easy to test as they are decoupled
- Reusable: easy to break down and reuse

Most of the problems came from querying some data, load all aggregate tree cost too much time and CPU. Sometimes a bypass is required. Look at this as a [[CQRS]], where you return a DTO specific for that case of use. Be careful because:
- It turns specific for that usage
- Be aware of don't split your business logic across the layers

## Literature
[[Article - Performance is a feature]]