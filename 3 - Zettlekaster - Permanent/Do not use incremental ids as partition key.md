Date: 2026-02-03
Tags: [[database partition]]
Source: [[Article - Can using incremental (but unique) IDs as a partition key create hot partitions in DynamoDB?]]

When database hash engine hashes id 1001 and 1002

1001 -> d89f3a35931c386956c1a402a8e09941
1002 -> 9103c8c82514f39d8360c7430c4ee557

They are not the same partition, be careful.