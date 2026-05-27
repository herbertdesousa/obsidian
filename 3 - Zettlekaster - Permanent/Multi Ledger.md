Date: 2026-02-03
Tags: [[data replication]]
Source: [[Book - Designing Data Intensive Applications]]

Like [[Single Ledger]], but with more than one ledger.

Useful when many writes incoming into the a single ledger is too much.

Usually they are architect across different data centers:

data center 1: Ledger -N-> Followers
data center 2: Ledger -N-> Followers

Features:
- Handling with conflicts: ...
- Topologies: ...
