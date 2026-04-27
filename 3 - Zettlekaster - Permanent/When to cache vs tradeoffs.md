Date: 2026-02-03
Tags: [[architecture]], [[caching]]
Source: [[Article - Caching Strategies in Java Applications Redis vs Hazelcast in Production]]

When to cache:
- Your database is hot and data doesn't change too frequently
- Your 3rd API have high cost and you could freeze a state of it
- Your algorithm is expensive, it cost 2-3 seconds to process.

Trade offs:
- Bad caching cause stale data with incorrect business decisions
- Architecture complexity