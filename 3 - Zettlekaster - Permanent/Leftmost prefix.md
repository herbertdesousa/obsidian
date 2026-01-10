Date: 2025-06-30
Tags: [[database]]

Creating a composed index like
`create index table(a, b)`

This uses index
`select * from ... where a = `

This does not use index
`select * from ... where b = `

The reason why is the way b-tree is created, they are a tuple of (a, b).
