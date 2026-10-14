# Soc Ops Workspace Instructions

## Mandatory Development Checklist

Before completing a change:

1. **Lint:** Run the configured lint/checkstyle command. No lint tool is currently configured; report that clearly if it remains unavailable.
2. **Build:** Run `cd socops && ./mvnw clean package` when build or dependency configuration changes.
3. **Test:** Run `cd socops && ./mvnw test`.
4. **Frontend:** For UI changes, run `cd socops && ./mvnw spring-boot:run` and verify `http://localhost:8080`.
5. Report any skipped validation and the reason.

## Project

Soc Ops is a Java 21, Spring Boot 3.4 social Bingo game. The application is in `socops/`; workshop docs are in `workshop/` and its `es/` and `pt_BR/` translations.

- Java, models, services, and controllers: `socops/src/main/java/com/socops/`
- Thymeleaf templates: `socops/src/main/resources/templates/`
- Static assets and shared CSS: `socops/src/main/resources/static/`
- JUnit tests: `socops/src/test/java/`
- Maven configuration: `socops/pom.xml`

Keep business rules in services/models, request wiring in thin controllers, and presentation in templates. Reuse existing APIs and avoid unnecessary dependencies or abstractions.

## Conventions

- Follow the existing package structure, dependency injection patterns, and Java 21 style.
- Do not modify generated output under `socops/target/`.
- Use utility classes documented in `.github/instructions/css-utilities.instructions.md`; keep shared styles in `static/css/app.css`.
- Follow `.github/instructions/frontend-design.instructions.md` for substantial UI work. Keep interfaces responsive, accessible, and stable on mobile and desktop.
- Make focused changes, preserve unrelated worktree changes, and update tests/docs when behavior or workflows change.
- Do not commit or create branches unless explicitly requested.
