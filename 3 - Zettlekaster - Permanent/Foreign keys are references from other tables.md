Date: 2025-05-26
Tags: [[database]]

In depth:
- RDBMS used to create indexes to foreign keys to fast lookup 
- Locks preventing race condition

Should not be used always:
- Performance in insert operations, once to rearrange indexing and other operations because of the foreign keys could take more time inserting a new register.
- Legacy apps that don't respect ACID.
- Microservices boundaries, tables where don't fit relationship between services.