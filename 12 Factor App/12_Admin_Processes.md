# 12. Admin Processes

**Admin processes** are one-off tasks run in the same environment as the app, but not part of normal operation.

Examples:
- Database migrations
- Data seeding
- Running a console for debugging

Run using the **same codebase, configuration, and backing services** as the app to ensure consistency and reduce environment-related issues.

## Key points

- Admin processes should be run in the same environment and with the same configuration as production to avoid surprises.
- Automate common admin tasks where possible and provide documented commands for operations teams.
