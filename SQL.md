# SQL

### Database Basis
+ Database
+ Table
+ Column: field
+ Datatype
+ Row: record
+ Keys:
  - Primary key:
  - Foreign key:

### Primary key
+ multiple column can be used together as a primary key
+ the data structure for primary key is B-tree.

#### what makes a column a primary key:
+ Unique
+ not Null
+ immutability
+ not reusable


### SQL statement basic:
+ terminate statements by semicolon
+ SQL statement is case-insensitive
+ extra whitespace will be ignored

#### Order of SELECT clause
+ SELECT
+ FROM
+ WHERE
+ GROUP BY
+ HAVING
+ ORDER BY

## retrieving data -- SELECT .. FROM
#### concatenating fields
\+ or ||
#### mathematical calculation
\+, -, *, \\
#### set alias
+ AS

## sorting data -- ORDER BY .. DESC/ACS
+ ORDER BY should be the last clause in your SELECT statement
+ it is okay to sort by non-selected columns
+ the sort orders is case-insensititve

## filterig data -- WHERE
#### WHERE clause operators:
+ BETWEEN
+ IS NULL
TBD

#### Combine WHERE clauses:
+ AND
+ OR
+ IN
+ NOT

#### wildcard filtering
+ LIKE
+ %
+ _
+ []

## Data Manipulate Functions
TBD

## Aggregation
+ AVG()
+ COUNT()
+ MAX()
+ MIN()
+ SUM()
we can use ALL, DISTINCT to modify the result

## Grouping -- GROUP BY
use HAVING instead of WHERE when filtering groups

## Joins
+ Cross Join
+ Self Join
+ INNER JOIN/ OUTER JOIN/ LEFT JOIN/ RIGHT JOIN

## Combining Queries
+ UNION
+ UNION ALL

## Inserting data -- INSERT
TBD

## UPDATE and DELETE

## CREATE TABLE and ALTER TABLE and DROP TABLE

## Views
Views are virtual tables.

+ CREATE VIEW

## Constraints

## Indexes

## Stored Procedures

## Triggers








  
