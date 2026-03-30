# 4. Backing Services

**Backing services** are any services that the app consumes over the network as part of its normal operation.

- Examples: databases, message queues, caching systems, external APIs
- Treat services as **attached resources** that can be swapped out without requiring code changes.
- Connect using **configuration** (e.g., environment variables) rather than hardcoding connection details.

Example of Backing Services:
- **Database**: PostgreSQL, MySQL, MongoDB
- **Message Queue**: RabbitMQ, Apache Kafka
- **Caching System**: Redis, Memcached
