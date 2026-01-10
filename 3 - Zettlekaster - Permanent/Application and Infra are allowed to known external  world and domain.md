Date: 2025-03-25
Tags: [[DDD]]

Big picture
External → [Application → Domain ← Infra] ← External
or
External → [Presentation → Application → Domain ← Infra] ← External

Rules:
- **Domains** are isolated from the rest of the world
- **Application** may know **Domain** and **External World** if **Presentation** doesn't exists
- **Infra** may know **Domain** and **External World**

You can use interfaces to separate layers tight like [Domain <- Infra]

## Related
[[Adapters may return DTOs instead of Domain Entities]]