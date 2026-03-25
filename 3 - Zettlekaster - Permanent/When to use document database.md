Date: 2026-03-24
Tags: [[database]]
Source: [[Book - Designing Data Intensive Applications]]

In pespective of data:

- Application usually needs to fetch the **whole data** as a single unit. Many-to-one relations are loaded at once.
  - Example: Vilela ar budgets
- A high [[Impedance Mismatch]]
- The require of schema on read. See [[Schema on read vs Schema on write]]
  - Example: Many services consuming same data souce in many different formats.

But be careful, you don't need a mongo to use document databases, [[Postgres is all you need]].
