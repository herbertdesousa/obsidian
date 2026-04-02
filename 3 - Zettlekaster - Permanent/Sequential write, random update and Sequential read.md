Date: 2026-02-03
Tags: [[performance]], [[hardware]]

Sequential write: Fast. Append only approaches like [[WAL Tables]] uses it.
Random update: Slow. HD needs to seek for the data and overwrite it. [[Write aplification on SSDs]] occours.
Sequential read: Fast. Write a single unit on memory. [[LSM Tree]] benefits of it.
