Date: 2026-02-03
Tags: [[performance]], [[database]]

Scan the whole table cost O(n), indexes B-trees which allow database query costing O(log n) on reads.

For writes, the perspective is completely different:
- Database has a additional data structure to manage and commit data
- Storage is impacted
- [[Write aplification on SSDs]] because of the random updates.