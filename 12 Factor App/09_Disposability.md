# 9. Disposability

The app should be designed to **start up and shut down quickly**, allowing for rapid scaling and deployment.

- Processes should be **disposable** — they can be started or stopped at any time without affecting overall functionality.
- This enables easier failure recovery — any instance can be replaced without impacting the system.
- Example: `docker stop ...` sends SIGTERM for graceful shutdown; if not stopped in time, SIGKILL forcefully terminates.
