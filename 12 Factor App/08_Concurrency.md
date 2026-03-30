# 8. Concurrency

Each instance of the app can serve multiple requests. On high influx of requests, scale up by:

- **Vertical scaling**: Increase resources (may require restart and cause downtime)
- **Horizontal scaling**: Run multiple app instances

Horizontal scaling requires:
- A **load balancer** to distribute traffic across instances (e.g., Nginx, HAProxy, cloud load balancers)
- **Stateless** app design so any instance can handle any request without relying on previous interactions
