Date: 2025-03-28
Tags: [[DDD]]


In the scenario
```ts
enum Status { APPROVED, REFUSED, PENDING }

class Customer { status: Status; }

// only use 
customer.status = Status.APPROVED
if (customer.status == Status.APPROVED) { ... }
```

You just have the status use for comparison and value setting, you don't really need a value-object, [[KISS]].