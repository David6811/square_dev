# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Java Maven project that demonstrates integration with Square's API using their AsyncSquareClient. The project contains:

- **Main application**: `Quickstart.java` - demonstrates fetching location data from Square API
- **Simple example**: `App.java` - basic "Hello World" application
- **Configuration**: Uses `config.properties` for storing Square API access token
- **Testing**: Basic JUnit 3.8.1 setup with minimal test coverage

## Development Commands

Since this is a Maven project, use standard Maven commands:

```bash
# Install dependencies
mvn dependency:resolve

# Compile the project
mvn compile

# Run tests
mvn test

# Package the application
mvn package

# Clean build artifacts
mvn clean

# Run the main Quickstart application
mvn exec:java -Dexec.mainClass="com.square.examples.Quickstart"

# Run the simple App
mvn exec:java -Dexec.mainClass="com.square.examples.App"
```

## Architecture Notes

- **Package structure**: `com.square.examples` - follows standard Java package conventions
- **Configuration management**: API tokens stored in `src/main/config.properties` (loaded via classpath)
- **API client**: Uses Square's AsyncSquareClient with sandbox environment
- **Error handling**: Comprehensive exception handling for Square API errors
- **Async patterns**: Uses CompletableFuture with `thenAccept()` and `exceptionally()` for async operations

## Key Dependencies

- Square Java SDK v45.1.0.20251016 (`com.squareup:square`) - AsyncSquareClient for API integration
- JUnit 3.8.1 for testing

## Important Files

- `pom.xml` - Maven configuration and dependencies
- `src/main/config.properties` - Contains Square API access token
- `src/main/java/com/square/examples/Quickstart.java` - Main Square API integration example
- `src/test/java/com/square/examples/AppTest.java` - Basic test structure