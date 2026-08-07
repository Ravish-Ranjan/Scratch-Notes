# Basics

1. 3 schema architecture
  1. external (view)
  2. conceptual (schema)
  3. physical (storage)
2. Type of dbms
  1. network
  2. object oriented
  3. hierarchical
  4. relational
3. primary components of dbms
  1. db engine
  2. query processor
  3. transaction manager
  4. storage manager
  5. db schema
4. Normalization : reduucing redundancy
5. Keys
  1. By complexity : simple, composite
  2. By value calculation : derived, simple
  3. By count : single, multivalu
6. Types of Keys
  1. candidate key (minimal superkey)
  2. primary key
  3. alternate key
  4. foreign key
  5. superkey : set of key which can uniquely idenity row (candidate + non-key)
  6. prime : part of a candidate key
  7. non-prime
7. Constrains
  1. Key constraint : every row can be uniqly identified (unique and primary key)
  2. Entity integrity constrain : specific, valid object represented by each row (primary key can't be null)
  3. Referencial key constrain : a foreign key is referenced from primary key
  4. Domain constraint : type, format of data a attribute can have
8. SQL execution order
  1. `from` > `where` > `group by` > `having` > `select` > `order by` > `offset` > `limit`
9. Relationship type in dbms
  1. one to one
  2. one to many
  3. many to many
10. Index  : a data structure for fast row access
11. Joins in dbms
  1. Logical
    1. inner join
    2. left outer
    3. right outer
    4. full outer
  2. operational join
    1. theta join (based on condition)
      1. equi join (based on equality)
        1. natural join (based on attribute name)
  3. Cross join (multiplying join)
  4. structural join (self join)

 