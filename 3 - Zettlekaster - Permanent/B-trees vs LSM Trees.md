Date: 2026-02-03
Tags: [[data structures]], [[database]]

Those two data structures powers up databases, but they have specially use cases:

- B-tree are faster for reads, indexes on PostgreSQL use a variant of B-trees called B+trees for example, they guarantee organized data when searching, but requires sort on write [1].
- [[LSM Tree]] are faster for writes but slow for reads, [[Write intensive applications]] cover it.
- [[LSM Tree]] uses more space on disk once data is more fragmented.
- [[LSM Tree]] compaction process can impact write/read ratio over concurrent process.

[1] - [[How indexes on database affect write performance]]
