# Handy plugins for Maven

This document provides a list of handy plugins that can enhance your Maven build process. These plugins can help with various tasks such as code quality checks, dependency management, code generation, database migration, and deployment.

## Dependency & Version Management
- **Versions Maven Plugin**: Helps manage and update project dependencies and plugins to their latest versions.
- **Maven Deploy Plugin**: Facilitates the deployment of artifacts to remote repositories.

## Build & Release Automation
- **Maven Release Plugin**: Automates the release process of your project, including versioning and tagging in version control.
- **Apache Maven Enforcer Plugin**: Enforces project rules such as dependency versions, banned dependencies, and more.
- **Apache Maven Compiler Plugin**: Compiles your project's source code.
- **Maven Assembly Plugin**: Creates distributable packages (e.g., ZIP, TAR) containing your project and its dependencies.
- **Exec Maven Plugin**: Allows execution of system and Java programs.

## Code Generation & Annotation Processing
- **JOOQ Codegen Maven Plugin**: Generates Java code from your database schema for type-safe SQL.
- **OpenAPI Generator Maven Plugin**: Generates API client/server code from OpenAPI specifications.
- **MapStruct Annotation Processor**: Generates type-safe bean mapping code during compilation.

## Database & Migration
- **Liquibase Maven Plugin**: Manages database schema migrations and versioning.

## Formatting & Indexing
- **Formatter Maven Plugin**: Automatically formats your code according to a specified style (e.g., Eclipse).

## Testing & Quality Assurance
- **Surefire Plugin**: Runs unit tests and generates test reports.
- **Maven Failsafe Plugin**: Runs integration tests during the integration-test phase of the build lifecycle.
- **JaCoCo :: Maven Plugin**: Provides code coverage reports for your tests.
- **Maven Checkstyle Plugin**: Integrates Checkstyle into the Maven build process to ensure code style compliance.
- **SonarQube Scanner for Maven**: Analyzes code quality and provides reports on bugs, vulnerabilities, and code smells.

## Documentation & Reporting
- **Maven Site Plugin**: Generates project documentation and reports in a structured format.
