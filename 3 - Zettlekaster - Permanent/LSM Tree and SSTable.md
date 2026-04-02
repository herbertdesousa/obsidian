Date: 2026-02-03
Tags: [[data structures]]
Source: [[Book - Designing Data Intensive Applications]]

LSM Tree is a data structure focused on handle massive writes. It works like:
1. Memtable: Write, sorted, on RAM. Usually a tree.
2. SSTable: Once Memtable is full, the data is streamed on sequential write on disk. (Sequential writes are fast. [1] [2])
3. Compaction: In background, a task catch SSTables and merge smaller into bigger SSTables.

The tradeoff: Search for a key requires: look though Memtables and all SSTables


[1] - [[Sequential write, random update and Sequential read]]
[2] - [[How SSL Tables imply non write aplification]]
