Date: 2026-02-03
Tags: [[data partition]]
Source: [[Book - Designing Data Intensive Applications]]


**Key Range**: based on continuous data, like date on time-series. [[Do not use incremental ids as partition key]]
e.g. year-month-day key
Pros:
- Do not need rebalacing partitions as partition grows, because it grows infinitely 
- Data is sorted, scans is easy
Cons:
- Choose a bad key, it all falls apart
- N partitions, require more resources
- Hot spots, specially with timestamp key

**Hashing Key**: Pre-defined amount of partitions
e.g.: Hash some information, maybe using md5, then 0..100 -> partition 1, 101..200 -> partition 2
Pros:
- Fixed amount of resources
- Uniform distribution of items,
Cons:
- Scatter/Gather, data is not sorted
- Add new partitions requires rebalacing

Do not use hash mod N partition key