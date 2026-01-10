Date: 2025-03-25
Tags: [[patterns]], [[DDD]] 

By adapters returning DTO, you have the ability to [[Initiate with detached and nodes instead of connected ones]], gaining more flexibility. The reason why for this is because if a property in your domain has just need to be created, and your adapter don't have the source to that. Then you have to migrate this to a DTO.

Let's say provider implementations follow an interface:

```
interface Provider {
  fetch(): Promise<User>
}
```

When User has too many fields that provider implementation is not enough to cover. Your app integration just broken.

Instead, you use can, increasing the level of complexity:
- 1. Create your own map in application services
- 2. Create your own class mapper
