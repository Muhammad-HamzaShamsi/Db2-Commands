# 🗄️ IBM Db2: Commands Cheat Sheet

![IBM Db2](https://img.shields.io/badge/IBM-Db2-052FAD?logo=ibm&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-reference-4479A1)
![Type](https://img.shields.io/badge/type-cheat%20sheet-informational)

A quick reference of **IBM Db2** commands from beginner to advanced, collected while administering Db2 in enterprise environments.

📄 **Full command list:** [`Db2-Commands.txt`](Db2-Commands.txt)

## About Db2

IBM Db2 is an enterprise relational database known for performance, scalability and strong security. It runs on-premises, on IBM Cloud and in containers.

- **Editions:** Community, Standard, Advanced Enterprise, Db2 on Cloud, Db2 Warehouse
- **Key technologies:** BLU Acceleration (in-memory columnar), pureScale (clustering), data federation, ML integration
- **Use cases:** OLTP systems, data warehousing and analytics, hybrid workloads, big data and IoT

## Beginner

```sql
CONNECT TO <db> USER <user> USING <password>;
CREATE DATABASE <db>;
LIST DATABASE DIRECTORY;
LIST TABLES FOR SCHEMA <schema>;
CREATE TABLE <table> (id INT NOT NULL PRIMARY KEY, name VARCHAR(100));
INSERT INTO <table> (id, name) VALUES (1, 'Hamza');
SELECT * FROM <table>;
UPDATE <table> SET name = 'X' WHERE id = 1;
DELETE FROM <table> WHERE id = 1;
DROP DATABASE <db>;
```

## Intermediate

```sql
ALTER TABLE <table> ADD COLUMN <col> <type>;
CREATE INDEX <idx> ON <table> (col1, col2);
DROP INDEX <idx>;
GRANT SELECT, INSERT ON <table> TO <user>;
REVOKE SELECT, INSERT ON <table> FROM <user>;
```

## Advanced / administration

```sql
BACKUP DATABASE <db> TO <dir>;
RESTORE DATABASE <db> FROM <dir>;
ROLLFORWARD DATABASE <db> TO END OF LOGS AND COMPLETE;
CREATE VIEW <view> AS SELECT col1, col2 FROM <table> WHERE ...;
RUNSTATS ON TABLE <schema>.<table> WITH DISTRIBUTION AND DETAILED INDEXES ALL;
REORG TABLE <schema>.<table>;
UPDATE DATABASE CONFIGURATION FOR <db> USING <param> <value>;
EXPORT TO file.del OF DEL SELECT * FROM <table>;
IMPORT FROM file.del OF DEL INSERT INTO <table>;
LOAD FROM file.del OF DEL INSERT INTO <table>;
FORCE APPLICATION (<handle>);
```

> ⚠️ `DROP` and `FORCE APPLICATION` are destructive. Double-check the target before running them in production.
