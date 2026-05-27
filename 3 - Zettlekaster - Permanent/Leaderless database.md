Date: 2026-02-03
Tags: [[data replication]]

No ledger, just a bunch of nodes.

How to guarantee consistency? **Quorum** 

Given N nodes, W is number of writes, R is number of reads. The formula is:
> W + R > N 

When N = 3, you have to, at least, write to 2 nodes successfully to when reading (R) you reach 1 updated node.
ps: Is common to use N as odd number.

**Healing the data**
Read repair: When client faces out dated data, it can write update data to the node.
Anti entropy: Nodes looks for updated data in background.
