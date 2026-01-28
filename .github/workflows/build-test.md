---
name: Build and Test
on:
  workflow_dispatch:
permissions:
  contents: read
engine: copilot
network:
  firewall: true
  allowed:
    - defaults
    - github
    - java
---

# Build and Test Java Project

You are an AI agent tasked with building and testing this Java project.

## Instructions

1. First, examine the project structure to determine the build system:
   - Look for `pom.xml` (Maven)
   - Look for `build.gradle` or `build.gradle.kts` (Gradle)

2. This project uses **Maven** (pom.xml is present).

3. Build the project:
   ```bash
   ./mvnw clean compile -DskipTests
   ```
   If `mvnw` is not available, use:
   ```bash
   mvn clean compile -DskipTests
   ```

4. Run the tests:
   ```bash
   ./mvnw test
   ```
   If `mvnw` is not available, use:
   ```bash
   mvn test
   ```

5. Report the results:
   - If the build succeeds, report success with a summary of the tests run
   - If the build fails, report the error and try to diagnose the issue

## Success Criteria

- The project compiles without errors
- All tests pass (or report which tests failed if any)
