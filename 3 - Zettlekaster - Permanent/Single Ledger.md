Date: 2026-02-03
Tags:  [[data replication]]
Source: [[Book - Designing Data Intensive Applications]]

One ledger: receives all writes and spread the data.
Many followers: receive reads and consume spread ledger data.

Ledger -N-> Followers

Communication can be:

**Sync**: Ledger keeps holding followers until all of them receive new data.
Pros: High consistency
Cons: High latency. Slowest follower holds everyone.

**Async**: Ledger sends async the changes to the followers.
Pros: Lower latency
Cons: Low consistency, replication lag and monotonic reads.
