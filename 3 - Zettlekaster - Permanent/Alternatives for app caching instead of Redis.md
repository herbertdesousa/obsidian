Date: 2025-04-09
Tags: [[scalability]], [[performance]], [[database]], [[alternatives tricks]]

First mind approach for application caching is Redis, it's really useful, but you can also:

[[WAL Tables]] with JSONB columns to use Postgres as _cacher_ (source: [[Article - Replace Redis with PostgreSQL]]).

Example:
```
-- Create the UNLOGGED table  
CREATE UNLOGGED TABLE cache (  
key TEXT PRIMARY KEY,  
value JSONB NOT NULL,  
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP  
);  
  
-- Seed with sample data  
INSERT INTO cache (key, value)  
VALUES  
('user:123', '{"id": 123, "name": "Alice", "role": "admin"}'::jsonb),  
('user:456', '{"id": 456, "name": "Bob", "role": "user"}'::jsonb);  
  
-- Add an index on the JSONB field for faster lookups (optional)  
CREATE INDEX idx_cache_value ON cache USING GIN (value);
```

The main tradeoff is that your database still being hit, if mirror to decrease database calls, it may not work for you.
