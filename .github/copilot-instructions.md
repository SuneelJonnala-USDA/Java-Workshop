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

## Design Guide

- Treat the Soc Ops game as a high-contrast social field tool: use a near-black foundation, warm white text and surfaces, and a single restrained accent for actions and status states.
- Prefer distinctive typography with a clear hierarchy: an expressive display face for product identity, a readable sans-serif for prompts, and monospace for labels, counters, and metadata.
- Build depth with borders, grids, spacing, and subtle texture rather than rounded card stacks, decorative gradients, or excessive shadows.
- Keep the primary workflow visible and immediate. Use clear action labels, familiar icons where helpful, and preserve existing game controls and DOM contracts unless behavior changes are required.
- Make selection, winning, disabled, hover, active, and keyboard-focus states visibly distinct. Never communicate an important state through color alone.
- Keep the bingo board square and stable across viewport sizes. Long prompts must wrap without causing layout shifts or horizontal scrolling.
- Test UI changes at desktop and narrow mobile widths, with keyboard navigation and reduced-motion preferences enabled where practical.
- Keep presentation in Thymeleaf and CSS, client-side interaction in the page script, and business rules in Java services/models. Avoid new frontend dependencies for CSS-only visual changes.
