Date: 2026-01-30
Tags: [[patterns]], [[distributed systems]]

Orchestration
Pros:
- Easy to trace: a single orchestration 
- Dump services: Order service just process, they don't know what is that
Cons:
- Single point of failure

The Saga Orchestration could be **standalone**, or **embedded** on the Order Service.


```mermaid
sequenceDiagram
    autonumber
    participant Client
    participant O as Order Service
    participant SEC as Saga Orchestrator
    participant P as Payment Service
    participant I as Inventory Service

    Client->>O: Place Order
    O->>SEC: Instantiate Saga

    rect rgb(240, 248, 255)
        Note over SEC: Step 1: Payment
        SEC->>P: Command: ProcessPayment
        P-->>SEC: Reply: PaymentSuccess
    end

    rect rgb(255, 250, 240)
        Note over SEC: Step 2: Inventory
        SEC->>I: Command: ReserveStock
        
        alt Stock Available (Happy Path)
            I-->>SEC: Reply: StockReserved
            SEC->>O: Update State: CONFIRMED
            
        else Stock Failure (Compensation Path)
            I-->>SEC: Reply: StockFailure
            
            Note over SEC: **Compensation Logic Triggered**
            
            rect rgb(255, 230, 230)
                SEC->>P: Command: RefundPayment
                P-->>SEC: Reply: RefundSuccess
            end
            
            SEC->>O: Update State: REJECTED
        end
    end
```