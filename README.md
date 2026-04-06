# TomEE DeltaSpike Project Template

A minimal Java web application template demonstrating **JSF**, **CDI**, and **Apache DeltaSpike** deployed on **Apache TomEE**.

## Architecture

- **GreetingService** — `@ApplicationScoped` CDI bean that produces greeting messages.
- **HelloWorldController** — `@WindowScoped` JSF backing bean (DeltaSpike) that captures user input and delegates to the greeting service.
- **JSF pages** — `helloWorld.xhtml` (input form with `<ds:windowId/>`) and `result.xhtml` (greeting output).

## Requirements

- **Java 25+**
- **Maven 3.6.3+**
- **Apache TomEE 10+** (Jakarta EE 10)

## Build

```bash
mvn clean verify
```

## Deploy

Deploy the generated `target/tomee-ds-project-template.war` to a TomEE 10+ instance, then open:

<http://localhost:8080/tomee-ds-project-template/helloWorld.xhtml>

## Quality Plugins

| Plugin       | Purpose                              |
|--------------|--------------------------------------|
| Compiler     | `-Xlint:all`, fail on warnings       |
| Enforcer     | Java 25+, Maven 3.6.3+, dependency convergence, ban javax.* |
| Checkstyle   | Code style enforcement (see `checkstyle.xml`) |
| RAT          | Apache 2.0 license header verification |
| Surefire     | Test execution                       |
| JaCoCo       | Code coverage reporting              |
| Javadoc      | API documentation generation         |

## Testing

CDI SE tests use the [Dynamic CDI Test Bean Addon](https://github.com/os890/dynamic-cdi-test-bean-addon)
with `@EnableTestBeans` for lightweight container bootstrap and automatic bean discovery.

## License

This project is licensed under the [Apache License, Version 2.0](LICENSE).
