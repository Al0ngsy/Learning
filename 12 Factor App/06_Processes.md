# 6. Processes

## Key Concepts

### Stateless Processes

- Design the app to be **stateless**, so any instance can handle any request without relying on previous interactions.
- This enables better **scalability and resilience**, as any instance can be replaced or scaled without affecting functionality.
- **Stateful data** should be stored in a backing service (database, cache) accessible by any app instance.
