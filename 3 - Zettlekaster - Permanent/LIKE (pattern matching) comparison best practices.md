Date: 2025-07-10
Tags: [[database]], [[performance]]


Following the [[Leftmost prefix]], creating this index:
```sql
CREATE INDEX table(a, b)
```

With LIKE
``` sql
a LIKE 'term%' -- uses index
a LIKE '%term' -- doesnt use indexes
b LIKE 'term%' -- doesnt use indexes
b LIKE '%term' -- doesnt use indexes
```

With ILIKE 
```sql
a ILIKE 'term%' -- doesnt use index
a ILIKE '%term' -- doesnt use index
```
When to use it? well, given a few rows... it's better make a 'brute force' comparison instead the cost of create a FTS index.

Lowercase is an option when ignoring case is required
```sql
CREATE INDEX LOWER(a)
a LIKE 'LOWER(term%)' -- use index
```

FTS (full text search) is also an option when the comparison you want needs to be prefix or suffix or even into the words.
INDEX GIN: larger index, but faster
INDEZ GiST: smaller index, but slower