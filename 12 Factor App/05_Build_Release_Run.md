# 5. Build, release, run

Clear separation between the build, release, and run stages of the app's lifecycle is essential.

- **Build stage**: Compiling the code and packaging it into a deployable artifact (e.g., a Docker image, a JAR file, or a ZIP file).
- **Release stage**: Combining the build artifact with the configuration to create a release that can be deployed to production. Each release should be uniquely identifiable (e.g., by a version number or a Git commit hash) and immutable.
- **Run stage**: Executing the app in the defined environment (dev, staging, production with its own environment variables).

## Key points

- Ensure builds are reproducible and releases are immutable to enable easy rollbacks.
- Keep configuration separate from the build artifact (use environment variables or external config stores).
- Automate the pipeline (CI/CD) to reduce manual steps and human error.
