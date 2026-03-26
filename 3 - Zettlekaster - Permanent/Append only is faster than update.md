Date: 2026-03-26
Tags: [[database]], [[performance]]
Source: [[Book - The pragmatic programmer]]

Many databases benefits from append-only, like:
- Postgres [[WAL Tables]]
- Bitcask: Distributed NoSQL key-value database

Why?
- Updates are dangerous concurrency needs to be considered
	That's the reasons [[Functional paradigms create a new value instead of changing existing one]] 
- Expensive, seek and then update

