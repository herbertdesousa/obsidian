Date: 2026-02-03
Tags: [[database]]

High throughput, read/writes performance database

RAM: Keeps the `KeyDir`, which is a hashed key to the value on disk, storing: file id, value offset and value size.
Disk: It stores sequentially the data on disk

Writes: Append at the end (append-only) the data on insert or updates. [[Append only is faster than update]]
Reads: Look for key hashed on RAM, and then perform O(1) search on disk.

GC: Garbage collection removes periodically data from the disk 

Useful scenarios:
- When dataset's are too large to fit in memory. But number of unique keys are small than RAM.

Not useful:
- Directly change data on database: With Bitcask, you need to pull the whole object into application, change it, and then store it again.