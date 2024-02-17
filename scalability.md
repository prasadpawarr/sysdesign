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
