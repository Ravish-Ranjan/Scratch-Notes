# Intermediate

1. Transactions
  1. ACID properties : atomicity, consistency, isolation, durability
  2. Procedures : function with one or more queries
  3. triggeres : auto triggereing procedures base don an event
2. Union vs Union all
  1. union : combine result of 2 queries and remove duplicate
  2. union all : combine result of 2 queries but doesn't remove duplicate
3. Normalization : process of reducing redundancy in db to avoid anomalies
  1. 1NF : `atomic data, no multiple valued attribute`
  2. 2NF : in `1NF` && `every non key attribute is fully dependent on primary key` (auto done in simple perimary key)
  3. 3NF : no transitive dependecy
    1. non-key -> non-key ❌
    2. key -> non-key **✓**
  4. BCNF :
    1. key -> non-key where key is super key
    2. non-prime -> prime ❌
  5. 4NF : no more than one multi valued dependecies
    1. table (A,B,C) : A->B (one-to-many), A->C (one-to-many) ❌
      - solution : table1(A,B) A->B, table2(A,C) A->C
  6. 5NF : no join depedency, if table cab be generate from join -> decompose it
4. Deadlock in DB : when 2 or more transaction are stopped because of resources aquired by other - prventions
  1. lock ordereing : ensure the transaction take lock in predefined order
  2. timeout : time to live preemption
  3. deadlock detection
5. Cursor pointer to the result set of a query
  - implicit : auto generated on query 
  - explicit : can be maually generated
6. Db lock types
  1. shared lock : for reading data
  2. exclusive lock : for writing data
  3. intent lock : signal of intent by transaction to lock resource
  4. update lock : intent by transaction to update resource
7. Index type
  1. single column : on only one column
  2. composite : on multiple columns at once
  3. unique : column have unique value on each row
  4. clustered : it organizes the table record, can only be one
  5. non-clusted : creates seprate data structure that holds pointer to data, can be multiple
8. View
  1. pure : dymanic result on select, doesn't store result
  2. materialized : precompiled faster, stores result
9. Procedure vs function


| Procedure                             | Function                               |
| ------------------------------------- | -------------------------------------- |
| may or may not return value           | must return only one value             |
| `call` / `execute`                    | called inside select, where, etc query |
| read, update, delete                  | read only                              |
| can call other function and procedure | can only call function, not procedure  |
| can do try-catch                      | can't do error control                 |


 