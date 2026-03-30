# 11. Logs

The app should **treat logs as event streams** and write to permanent storage, not local storage.

- The app should **not** be responsible for managing log files or log rotation.
- Send logs to a **centralized logging system** (e.g., ELK Stack, Splunk, Datadog).
- Aggregating logs from all instances enables better monitoring and troubleshooting.
