Date: 2026-02-03
Tags: [[database partition]]
Source: [[Article - Can using incremental (but unique) IDs as a partition key create hot partitions in DynamoDB?]]

Given an example of order service, the partition key is date. On a regular day the distributions of partitions are close to the same, but in a Black Friday it suddenly grow fast, a huge partition, this is a hot partition.
