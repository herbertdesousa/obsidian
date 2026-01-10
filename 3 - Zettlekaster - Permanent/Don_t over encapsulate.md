Date: 2025-05-30
Tags: [[patterns]]

Given a class User with status attribute which is a enum, it could, for example, be PENDING or REVIEW or COMPLETE.

When a statement to compare if user status is PENDING, you don't need to encapsulate

```ts
if (user.isPending()) {} // it's unnecessary

if (user.status === USER_STATUS.PENDING) {} // better
```

Like this, you avoid boilerplates, be straight.

But, when you need to, let's say, for customer be pending needs to be in statuses PENDING and REVIEW

```ts
if (user.status === USER_STATUS.PENDING && ) {} // you gonna replicate this logic across multiple files

if (user.isPending()) {} // better
```

This way really encapsulates the PENDING.