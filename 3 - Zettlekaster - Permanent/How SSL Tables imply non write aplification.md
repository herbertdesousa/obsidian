Date: 2026-02-03
Tags: [[hardware]], [[data structures]]

As [[LSM Tree]] says. A whole SSTable is inserted at once, a sequential write [1].
SSD doesn’t need to write on another page and stale the past page [2]. SSDs garbage collector works less.

[1] Check out the difference between [[Sequential write, random update and Sequential read]].
[2] Read about [[Write aplification on SSDs]]
