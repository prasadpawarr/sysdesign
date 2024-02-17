# 17-feb-2024

## Databases

### Internals
PAGE:
- rows are stored in logical pages
- page size in postgres-8KB, mysql-16KB

HEAP:
- data structure that stores entire table (in pages on after another)
- expensive to read from HEAP

INDEX: 
- data structure (b-tree) that has pointers to HEAP
- tells you excatly which page to fetch from HEAP

### ROW store / ROW oriented
- 


### COLUMN store / Columnar 


### Indexing
- increases read perf, decrease write perf
- O(N) reads

#### Hash indexes
- better to keep in RAM than disk. 
- slow reads in disk, since data kept on random memory locations (hash value)
- write ahead log?
- range query still gives O(N)

