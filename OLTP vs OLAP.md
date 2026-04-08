Date: 2026-02-03
Tags: [[database]]
Source: [[Book - Designing Data Intensive Applications]]

OLTP: Online Transaction Processing
OLAP: Online Analytics Processing

OLTP handle with insertions, queries. Usually CRUD operations.
OLAP handles with aggregation, summing, averaging. Many data.

| Property             | Transaction processing systems (OLTP)             | Analytic systems (OLAP)                   |
| -------------------- | ------------------------------------------------- | ----------------------------------------- |
| Main read pattern    | Small number of records per query, fetched by key | Aggregate over large number of records    |
| Main write pattern   | Random-access, low-latency writes from user input | Bulk import (ETL) or event stream         |
| Primarily used by    | End user/customer, via web application            | Internal analyst, for decision support    |
| What data represents | Latest state of data (current point in time)      | History of events that happened over time |
| Dataset size         | Gigabytes to terabytes                            | Terabytes to petabytes                    |
