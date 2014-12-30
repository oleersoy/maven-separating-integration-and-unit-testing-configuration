
# Using Maven Profiles for Integration Test Configuration

## Objectives

- Create unit test specific configuration resources when running unit tests
- Create integration-test specific resources when running integration tests

## Enablers

[Maven Profiles](http://maven.apache.org/guides/introduction/introduction-to-profiles.html) will be used to configure the build such that it produces configuration settings that are specific to either integration or unit testing.  

## <a name="scenario"></a>Scenario

### Action

Execute the `unit-test` build profile with Maven by running `mvn test`.

### Process

To produce the result Maven takes the property values specified in `profiles/unit-test/hibernate.properties`, injects them into the template contained in `src/main/resources/hibernate.properties`, and saves resulting configuration to `src/target/classes/hibernate.properties`.

### Result

A hibernate configuration properties file, `src/target/classes/hibernate.properties` is created containing parameters that are specific to unit testing.

### Action

Execute the `integration-test` build profile with Maven by running `mvn clean test -P integration-test`.

### Process

To produce the result Maven takes the property values specified in `profiles/integration-test/hibernate.properties`, injects them into the template contained in `src/main/resources/hibernate.properties`, and saves resulting configuration to `src/target/classes/hibernate.properties`.

### Result

A hibernate configuration properties file, `src/target/classes/hibernate.properties` is created containing parameters that are specific to integration testing.

