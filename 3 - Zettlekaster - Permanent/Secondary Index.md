Date: 2026-02-03
Tags: [[data partition]]
Source: [[Book - Designing Data Intensive Applications]]

LSI - Local secondary index
Structure inside a partition, (aka sort key on dynamo) **keeps a key value or b-tree mapping on the partition**.
Pros
- Multi dimension flexibility
- Data is sorted
- Usually consistent, because it is synchronous write
Cons
- Search for secondary index, without primary index partition key, requires scatter-gather
- Write amplification, one more structure to be written 

GSI - Global secondary index
Structure outside a partition, usually a b-tree, it indexes across nodes
Pros
- Across nodes possibility, avoids scatter-gather
- Can be added/deleted anytime without impact nodes
Cons
- Usually eventual consistent
- Write amplification
- Requires more storage than LSI