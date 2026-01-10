Date: 2025-04-09
Tags: [[database]]

WAL means write-ahead log, they are tables that first write the data and then logs. It improves a lot the performance, with the tradeoff of loose the data in a crash between write and log saving.

## Relation
[[Article - Performance Impact setting a database to read only]]