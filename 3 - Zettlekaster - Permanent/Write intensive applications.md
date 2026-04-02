Date: 2026-02-03
Tags: [[database]], [[performance]]

- You definitely needs a NoSQL
    - Regular relational databases ensures consistency over availability, We can’t have both PACELC says that [1].
- Cassadra can helps you [2]. 
- Applications write intensive:
	- Real-time tracking like uber
	- Monitoring like prometheus
- Write intensive use [[data structures]] as [[LSM Tree]].


[1] - [[PACELC - PC EL and PA EC examples]]
[2] - [[Why cassandra is write fast?]]