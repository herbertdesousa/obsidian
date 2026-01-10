Date: 2025-07-08
Tags: [[database]]

In a given table with large amount of rows, queries turns slow, inserting is a shit, think in terms of [[scalability]]:

**Do I can avoid this table growth?**
Imagine a followers counting in a social app, instead of counting the relations in a ```
tb_relationship``` or something, save in the user profile the count itself.

**Do I can Index?**
Indexes can avoid queries to be slow, but be careful about insertions and deletions.

**Do I can partition?**
Partitioning splits your database table into multiple regions in the disk, I can be a good approach to large tables.
(not too much info about cons)

**Do I can shard?**
Sharding splits your database into multiple ones.
(not too much info about cons)

Give a step at the time.