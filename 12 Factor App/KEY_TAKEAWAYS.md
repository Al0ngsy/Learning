# 12 Factor App Key Takeaways

Use this as a quick checklist when designing or reviewing cloud-native services.

## The 12 Factors at a Glance

1. Codebase: one codebase tracked in version control per service.
2. Dependencies: declare and isolate all dependencies.
3. Config: store config in environment variables.
4. Backing Services: treat services as attached resources.
5. Build, Release, Run: keep these stages strictly separate.
6. Processes: execute the app as stateless processes.
7. Port Binding: export services via port binding.
8. Concurrency: scale out via the process model.
9. Disposability: favor fast startup and graceful shutdown.
10. Dev/Prod Parity: keep environments as similar as possible.
11. Logs: treat logs as event streams.
12. Admin Processes: run admin tasks as one-off processes.

## Practical Review Checklist

- Can this service be redeployed without manual machine setup?
- Is all runtime configuration externalized?
- Can any app instance handle any request?
- Are logs centralized and queryable?
- Are operational/admin tasks reproducible via commands?
