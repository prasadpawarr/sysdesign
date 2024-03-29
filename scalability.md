# 15-feb-2024

## scalability
service is scalable if increase resources in system, increases performance of system
### clones (multiple instances)
- horizontal scaling
- load-balancer distributes the load between multiple application servers
- user should get same result irrespective of which server served his request.
- user-related data like sessions, prof pictures etc must be stored in external persistent db.
- sessions - stored in external persistent in-memory cache (Redis)

### cache (in-memory)
- key-value store residing between application and data storage
- cached database queries:
    - query db > store result in cache
    - key: hash of query
    - cons: when to expire? for a change in data, which all queries to delete?

- cached database objects:
    - store the complete database obj in cache
    - get rid of obj when something changes
    - async processing possible
    - what to cache: user sessions, rendered blog articles.

## scale zero to millions

### nosql
use this when:

- app required super low-latency
- data is unstructured
- serialize and deserialize (json)
- store massive amount of data

### vertical scaling 
- scale up
- adding more power (CPU/RAM/storage)
- pros:
    - simple, easy to scale
    - good if less traffic
- cons:
    - hard limit
    - failover, redundancy not possible

### horizontal scaling
- scale out
- adding more servers
- pros:
    - good for large scale apps
    - provides redundancy incase of failure

### load balancers
- need for load balancer because of horizontal scaling

### db replication
- provides reliability, availability
- improves performance
- usually master-slave architecture
- master: supports only write-ops
- slave: supports only read-ops (multiple slaves - apps usually read heavy)

### summary
- Keep web tier stateless
- Build redundancy at every tier
- Cache data as much as you can
- Support multiple data centers
- Host static assets in CDN
- Scale your data tier by sharding
- Split tiers into individual services
- Monitor your system and use automation tools