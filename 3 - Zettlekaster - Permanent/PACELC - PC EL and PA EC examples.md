Date: 2025-10-30
Tags: [[architecture]]

## PC/EL - On partition consistency, else Low-Latency

**Without partition**
Send message to queue to replicate the data, without needing to wait to replication finish
![[Pasted image 20251030162419.png]]

**On partition**
With Leader health checking the replicas, if someone dies, stop writes to be proceeded.
![[Pasted image 20251030162427.png]]

## PA/EC - On partition availability, else Consistency

**Without partition**
Waits untill all writes to be done in all replicas
![[Pasted image 20251030162650.png]]

**On partition**
The queue of insertions acks the leaders, even with partition is possible to access the replicas
![[Pasted image 20251030162707.png]]


Source: [[Article - PACELC With examples]]