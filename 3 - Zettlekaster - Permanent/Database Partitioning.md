Date: 2026-02-03
Tags: [[database partition]], [[scalability]]

Partition is a technique to split physically table, index and other structures on disk and memory. It allow us to scale by increasing availability and isolating failures. 

**Partition features:**
- [[Horizontal vs Vertical partition]]
- [[Database partition techniques]]

Table is partitioned based on a  
- shard

Useful when:
- More than 10-20 GB table
- B-tree don't fit in memory
- Part of the data can be die. Like a time-serie where older data can be deleted.

Not useful when:
- Key is frequently changed requiring tuples be moved from on partition to another.
- When B-tree fits in memory.