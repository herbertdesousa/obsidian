Date: 2025-03-28
Tags: [[performance]]

When you handle with transaction with locks, as name says, it locks the table. Avoiding every other write to be write. If you take too much time to compute this transaction, you are creating a bottleneck.

Looks very stupid, but [[Avoid print large stuffs]] inside transactions, may take some problems.
