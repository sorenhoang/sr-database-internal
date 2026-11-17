# sr-database-internal

**Database Internals Deep Dive** is a single-page tracker for 179 database concepts in 23 groups. Groups 1–14 follow *Database Internals* (Alex Petrov): storage engines first, distributed systems second. Groups 15–23 apply that base to the NoSQL world, one data model per group. Other classic books and papers fill the gaps.

**Live:** https://sorenhoang.github.io/sr-database-internal/

## Usage

Open `index.html` in a browser. It has no build step and no dependencies.

- The left sidebar lists the groups. Expand one to see its concepts.
- Concepts are numbered top-down in sidebar order.
- Click a group or a concept to open it. Links like `#slotted-pages` and `#g-0` can be bookmarked.
- Concepts you haven't learned yet show **Coming soon**. The progress bar counts the learned ones.
- Each group shows the book chapters and papers it draws from.

## Adding content for a learned concept

Content lives in one file per group, `content/<group-slug>.js`, and each concept is registered by its slug:

```js
CONTENT["slotted-pages"] = `
  <p class="tldr">…</p>
  <h2>How it works</h2>
  <figure class="diagram"><svg viewBox="0 0 780 300">…</svg></figure>
`;
```

Load the file in `index.html` with `<script src="content/<group-slug>.js"></script>`, next to the comment that explains it. Once a concept has content, it switches from "Coming soon" to "Learned" and the progress counts update. Inline SVG diagrams use the `.diagram` classes in `index.html`, so they work in both light and dark mode.

## Groups

| # | Group | Concepts | Main sources |
|---|---|---|---|
| 1 | Foundations & DBMS Architecture | 7 | DI ch.1, Architecture of a Database System |
| 2 | Storage & File Formats | 8 | DI ch.3, CMU 15-445, PostgreSQL 14 Internals |
| 3 | B-Tree Indexes | 10 | DI ch.2, 4, 6 |
| 4 | LSM Trees & Log-Structured Storage | 9 | DI ch.7, DDIA ch.3 |
| 5 | Other Index Structures | 5 | Database System Concepts, Use The Index, Luke! |
| 6 | Buffer Management | 6 | DI ch.5, CMU 15-445 |
| 7 | Transactions & Recovery | 8 | DI ch.5, Gray & Reuter, ARIES |
| 8 | Concurrency Control | 11 | DI ch.5, DDIA ch.7 |
| 9 | Query Processing & Execution | 8 | Architecture of a Database System, CMU 15-445 |
| 10 | Query Optimization | 7 | Selinger 1979, Database System Concepts |
| 11 | Column Stores & Analytics | 7 | Abadi et al., CMU 15-721 |
| 12 | Replication & Failure Detection | 11 | DI ch.9, 11, 12, DDIA ch.5, Dynamo |
| 13 | Consistency & Consensus | 8 | DI ch.10, 11, 14, DDIA ch.8–9, Raft |
| 14 | Partitioning & Distributed Transactions | 10 | DI ch.13, DDIA ch.6, Spanner, Calvin, Percolator |
| 15 | NoSQL Foundations | 7 | NoSQL Distilled, DDIA ch.2, Seven Databases in Seven Weeks |
| 16 | Key-Value Stores | 7 | Dynamo, DynamoDB (2022), FoundationDB, The DynamoDB Book |
| 17 | In-Memory Data Stores | 7 | Redis in Action |
| 18 | Document Databases | 8 | MongoDB: The Definitive Guide, NoSQL Distilled |
| 19 | Wide-Column Stores | 8 | Bigtable, Cassandra, Cassandra: The Definitive Guide |
| 20 | Graph Databases | 7 | Graph Databases (Robinson, Webber & Eifrem) |
| 21 | Time-Series Databases | 6 | Gorilla, Prometheus TSDB |
| 22 | Search Engines | 7 | Introduction to Information Retrieval, Lucene in Action |
| 23 | Vector Databases | 7 | HNSW, FAISS, DiskANN |

## Reading list

**Books**
- *Database Internals*, Alex Petrov (O'Reilly, 2019). The spine of this tracker.
- *Designing Data-Intensive Applications*, Martin Kleppmann (O'Reilly). Chapter numbers here refer to the 1st edition.
- *Database System Concepts*, Silberschatz, Korth & Sudarshan (7th ed.)
- *Transaction Processing: Concepts and Techniques*, Jim Gray & Andreas Reuter
- *PostgreSQL 14 Internals*, Egor Rogov
- *SQL Performance Explained* / *Use The Index, Luke!*, Markus Winand
- *Readings in Database Systems* ("The Red Book"), Bailis, Hellerstein & Stonebraker
- *NoSQL Distilled*, Pramod Sadalage & Martin Fowler
- *Seven Databases in Seven Weeks*, Perkins, Redmond & Wilson (2nd ed.)
- *The DynamoDB Book*, Alex DeBrie
- *Redis in Action*, Josiah Carlson
- *MongoDB: The Definitive Guide*, Bradshaw, Brazil & Chodorow
- *Cassandra: The Definitive Guide*, Jeff Carpenter & Eben Hewitt
- *Graph Databases*, Ian Robinson, Jim Webber & Emil Eifrem
- *Introduction to Information Retrieval*, Manning, Raghavan & Schütze

**Papers & courses**
- *Architecture of a Database System*, Hellerstein, Stonebraker & Hamilton (2007)
- *ARIES*, Mohan et al. (1992)
- *A Critique of ANSI SQL Isolation Levels*, Berenson et al. (1995)
- *Access Path Selection in a Relational DBMS*, Selinger et al. (1979)
- *The Log-Structured Merge-Tree*, O'Neil et al. (1996)
- *Dynamo*, *Spanner*, *Calvin*, *Percolator*, *Raft*
- *Bigtable* (2006), *Cassandra* (2009), *Amazon DynamoDB* (2022), *FoundationDB* (2021)
- *Gorilla* (2015), *HNSW* (2016), *FAISS*, *DiskANN* (2019)
- *Are You Sure You Want to Use MMAP in Your DBMS?*, Crotty, Leis & Pavlo (2022)
- CMU 15-445 (Intro to Database Systems) and 15-721 (Advanced Database Systems), Andy Pavlo
