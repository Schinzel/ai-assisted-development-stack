# Stack Experiments (2025)

Anecdotal experiences from building the same type of application (workflow/warehouse management)
with different stacks using AI-assisted development.

## wms2 — Kotlin + Javalin + Custom SSR + Exposed ORM

- **Backend**: Kotlin, Javalin (via custom "WebBlocks" wrapper)
- **Frontend**: Custom SSR template engine with component/block pattern, jQuery, vanilla JS
- **Database**: PostgreSQL, Exposed ORM (Kotlin DSL)
- **Architecture**: Vertical slices within multi-module monolith
- **Build**: Maven, fat JAR via shade plugin
- **Notable**: Custom annotation-based routing (@Page, @PageBlock, @PageBlockApi). Custom in-house framework layer on top of Javalin.

## wms3 — Kotlin + Spring Boot + Next.js SPA

- **Backend**: Kotlin, Spring Boot 3.3, Spring Data JPA
- **Frontend**: Next.js 14 (React 18), Tailwind CSS, Radix UI, TanStack Query/Table
- **Database**: PostgreSQL, JPA/Hibernate ORM, Flyway migrations
- **Architecture**: Layered backend + SPA frontend, OpenAPI-generated TypeScript client
- **Build**: Gradle (backend), Next.js/Webpack (frontend)
- **Notable**: Full type-safe contract via OpenAPI code generation. Two separate build systems.

## wms4 — Ruby + Sinatra + SSR

- **Backend**: Ruby 3.3, Sinatra 3.0
- **Frontend**: SSR with ERB templates, Tailwind CSS (CDN)
- **Database**: PostgreSQL (configured), in-memory DB for prototyping
- **Architecture**: Feature-based vertical slices, repository + DTO pattern
- **Build**: Bundler, Puma server
- **Notable**: Minimal dependencies (6 production gems). Dynamic feature loading via config.ru auto-mounting.

## wms5 — Kotlin + Ktor + Thymeleaf SSR

- **Backend**: Kotlin, Ktor 2.3, Netty
- **Frontend**: SSR with Thymeleaf, Alpine.js, Tailwind CSS (CDN)
- **Database**: PostgreSQL, Exposed ORM, HikariCP
- **Architecture**: Feature-based vertical slices (routes/service/repo/DTO/template per feature)
- **Build**: Gradle, Shadow JAR
- **Notable**: Kotlin coroutines for async DB. Testcontainers for integration tests.

## wms6 — Kotlin + Javalin + HTMX + JTE (skeleton)

- **Backend**: Kotlin, Javalin
- **Frontend**: HTMX, JTE templates
- **Database**: Not yet configured
- **Architecture**: Not yet implemented
- **Build**: Gradle
- **Notable**: Skeleton repo only — declared intent, no implementation.

## wms7 — Java + Javalin + HTMX + JTE + Raw SQL

- **Backend**: Java 21, Javalin 6
- **Frontend**: SSR with JTE, HTMX, Alpine.js, Tailwind CSS (CDN)
- **Database**: PostgreSQL, JDBI (raw SQL, not ORM)
- **Architecture**: Feature-based with file-system routing (folder structure = URL routes)
- **Build**: Maven, fat JAR via shade plugin
- **Notable**: Lombok, MapStruct, Vavr. Convention: class names (Get, Post, Put, Delete) determine HTTP method. Folders `pages_auth/` vs `pages_open/` for auth separation.

## workflow-management — Kotlin + Javalin + SvelteKit SPA

- **Backend**: Kotlin, Javalin 5.6, Koin DI
- **Frontend**: SvelteKit (Svelte 5), Vite, Tailwind CSS, Melt UI, XyFlow graphs
- **Database**: PostgreSQL, Exposed ORM, HikariCP
- **Architecture**: Modular monolith with vertical slices. 12 Gradle modules (logic + sites layers).
- **Build**: Gradle, fat JAR. Frontend pre-built as static files embedded in JAR.
- **Notable**: Custom Gradle task auto-generates TypeScript types from Kotlin DTOs. SvelteKit adapter-static for pre-rendering.

## poak — Java + Javalin + HTMX + JTE + Raw SQL

- **Backend**: Java 21, Javalin 6.7
- **Frontend**: SSR with JTE, HTMX, Alpine.js, Tailwind CSS (standalone CLI, no Node.js)
- **Database**: PostgreSQL, JDBI (raw SQL), Flyway migrations
- **Architecture**: Feature-based with file-system routing (same pattern as wms7, more mature)
- **Build**: Maven, fat JAR via shade plugin
- **Notable**: Vavr for functional patterns. Resend for email, AWS S3/R2 for files. Playwright + Testcontainers for testing. Constructor-as-action transaction pattern. Most mature of all repos.
