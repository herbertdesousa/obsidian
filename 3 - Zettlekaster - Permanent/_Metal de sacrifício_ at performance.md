Date: 2025-06-09
Tags: [[performance]], [[my paradigms]]

By improving performance, we may discovery new hidden issues that was invisible.

Case Example: At Peer, operating internal transfer between accounts was OK for CPU, because the bottleneck was in Cellcoin, our BaaS provider, but when I put a queue to async process the messages, the bottleneck was gone and other issues had turn the new issues.

![[Pasted image 20250616215925.png]]
