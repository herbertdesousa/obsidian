Date: 2026-02-03
Tags: [[data structures]]
Source: [[Book - Designing Data Intensive Applications]]

LSM Tree: Log-Structured Merge-Table
SSTable: Sorted String Table

LSM Tree is a data structure focused on handle massive writes. It works like:
1. At the first step, LSM writes on [[WAL Tables]] to prevent data loose.
2. MemTable: Write, sorted, on RAM. Usually a tree algorithm.
3. SSTable: Once MemTable is full, the data is streamed on sequential write on disk, which is fast [1] [2].
4. Compaction: In background, a task catch SSTables and merge smallers into biggers SSTables.

The trade off is query, it needs follow until find the value:
- Read from MemTable
- Read from Level 0 SSTables
- Read from older SSTables
In the worst scenario, data is on the last SSTable.


[1] - [[Sequential write, random update and Sequential read]]
[2] - [[How SSL Tables imply non write aplification]]
