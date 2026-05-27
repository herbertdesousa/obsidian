Date: 2026-02-03
Tags: [[data partition]]
Source: [[Book - Designing Data Intensive Applications]]

If you use hash(user-123) % 5, where 5 is number of partitions you have.

When you need to rebalace the partitions, like hash(user-123) % 6

hash(user-123) % 5 != hash(user-123) % 6

Past keys is dead.