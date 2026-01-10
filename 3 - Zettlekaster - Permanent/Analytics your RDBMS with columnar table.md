Date: 2025-06-23
Tags: [[database]]

Column based tables makes your table being store in blocks of columns, instead of typically rows, why? 
- Aggregating values is much faster
- Excel

But there is cons, a lot of them:
- Insert/Update/Delete a row is a shit
- Selecting multiple fields are poor
- Where with multiple cases are also bad

In summary, you'll never use it