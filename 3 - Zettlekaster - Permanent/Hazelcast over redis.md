Date: 2026-02-03
Tags: [[caching]]

Use hazelcast when:
- Zero network hops
- Store large objects 
- Hazelcast is PA/EC[1] while Redis is PC/EL
	- Over partition hazelcast priorize availability, while redis priorize consistency, this tradeoff causes lower throughtput 

[1] - [[PACELC - PC EL and PA EC examples]]
