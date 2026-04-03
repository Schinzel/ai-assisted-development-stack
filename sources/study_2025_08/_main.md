# Stack Experiments (2025)

Anecdotal experiences from building the same type of application (workflow/warehouse management)
with different stacks using AI-assisted development.


## Summary
AIs used:
- ChatGPT
- Gemini
- Claude Desktop

This is my observations from 2025. Gen AI models develop at a very high pace. 
What was true then might not be true a year later, but I suspect that same parameters will be true for at least a couple of years.

- What stood out: What AI thought was an efficient stack for AI assisted development is not correct.
  - AIs very strongly focused on what stack, technology or language has the most training data. 
  - AIs severally overestimates its capacity to handle more complicated build steps
  - AIs underestimates how well it handles more complicated set ups

My conclusions
- Complicated stacks, languages, techniques slow things down
- You need a certain threshold level of training data. After that, other aspects are much more
  important than more training data.

Surprises
- The stack that the AI got to decide on performed horribly. 
- That the Ruby stack by far was the most productive. 
  - I chose Ruby because it is described as an elegant language and being inspired by Smalltalk, a language that I admire.
  - I did not think it would perform well due to the limited 

## wms2 — Kotlin + Javalin + Custom SSR + Exposed ORM

- **Backend**: Kotlin, Javalin (via custom "WebBlocks" wrapper)
- **Frontend**: Custom SSR template engine with component/block pattern, jQuery, vanilla JS
- **Database**: PostgreSQL, Exposed ORM (Kotlin DSL)
- **Architecture**: Vertical slices within multi-module monolith
- **Build**: Maven, fat JAR via shade plugin
- **Notable**: Custom annotation-based routing (@Page, @PageBlock, @PageBlockApi). Custom in-house framework layer on top of Javalin.
- **Observations**: Developed an AI visual development approach using Playwright as feedback mechanism — AI could verify layout, colors, and alignment programmatically. Guide described as "intentionally minimal — as patterns emerge, they will be documented."

## wms3 — Kotlin + Spring Boot + Next.js SPA

- **Backend**: Kotlin, Spring Boot 3.3, Spring Data JPA
- **Frontend**: Next.js 14 (React 18), Tailwind CSS, Radix UI, TanStack Query/Table
- **Database**: PostgreSQL, JPA/Hibernate ORM, Flyway migrations
- **Architecture**: Layered backend + SPA frontend, OpenAPI-generated TypeScript client
- **Build**: Gradle (backend), Next.js/Webpack (frontend)
- **Notable**: Full type-safe contract via OpenAPI code generation. Two separate build systems.
- **Observations**: Stack explicitly chosen as "AI-optimized" — rationale was "maximum training data" (React/Spring Boot have largest AI datasets) and "component-based = natural units for AI code generation." Architecture decision to defer monorepo migration followed YAGNI principle. Despite the AI-optimization rationale, this was the heaviest stack attempted.

## wms4 — Ruby + Sinatra + SSR

- **Backend**: Ruby 3.3, Sinatra 3.0
- **Frontend**: SSR with ERB templates, Tailwind CSS (CDN)
- **Database**: PostgreSQL (configured), in-memory DB for prototyping
- **Architecture**: Feature-based vertical slices, repository + DTO pattern
- **Build**: Bundler, Puma server
- **Notable**: Minimal dependencies (6 production gems). Dynamic feature loading via config.ru auto-mounting.
- **Observations**: Dramatic shift toward simplicity after wms3. Pure server-side rendering, no SPA, no build pipeline for frontend. In-memory DB used for rapid prototyping before committing to PostgreSQL.

## wms5 — Kotlin + Ktor + Thymeleaf SSR

- **Backend**: Kotlin, Ktor 2.3, Netty
- **Frontend**: SSR with Thymeleaf, Alpine.js, Tailwind CSS (CDN)
- **Database**: PostgreSQL, Exposed ORM, HikariCP
- **Architecture**: Feature-based vertical slices (routes/service/repo/DTO/template per feature)
- **Build**: Gradle, Shadow JAR
- **Notable**: Kotlin coroutines for async DB. Testcontainers for integration tests.
- **Observations**: Established explicit parameters for AI-assisted development: "AI tractability" — architecture must be simple enough for AI to implement correctly 9/10 times on first attempt, otherwise it's too complex. Also "boring technology" — prefer mature, battle-tested tech with 1000+ Stack Overflow answers. Explored candidate patterns like contract-first development, declarative screens, and pure functions.

## wms6 — Kotlin + Javalin + HTMX + JTE (skeleton)

- **Backend**: Kotlin, Javalin
- **Frontend**: HTMX, JTE templates
- **Database**: Not yet configured
- **Architecture**: Not yet implemented
- **Build**: Gradle
- **Notable**: Skeleton repo only — declared intent, no implementation. Marks the pivot point to HTMX.

## wms7 — Java + Javalin + HTMX + JTE + Raw SQL

- **Backend**: Java 21, Javalin 6
- **Frontend**: SSR with JTE, HTMX, Alpine.js, Tailwind CSS (CDN)
- **Database**: PostgreSQL, JDBI (raw SQL, not ORM)
- **Architecture**: Feature-based with file-system routing (folder structure = URL routes)
- **Build**: Maven, fat JAR via shade plugin
- **Notable**: Lombok, MapStruct, Vavr. Convention: class names (Get, Post, Put, Delete) determine HTTP method. Folders `pages_auth/` vs `pages_open/` for auth separation.
- **Observations**:
  - Switched from Kotlin to Java, and from ORM to raw SQL (JDBI).
  - HTMX spike documented: replaced Alpine.js interval switching with pure HTMX. Response times were 10-20ms (imperceptible). Template isolation worked well (~80 lines vs 400-line monolith). But the halfway approach failed — "isolated templates but shared handler with conditionals — worst of both worlds."
  - Key AI insight: "CC struggled: Signal that the task boundaries weren't clean." When Claude Code had trouble, it signaled an architecture problem, not an implementation problem.
  - Established code standards for AIs: "Since AI might implement functions differently than expected, well-defined interfaces with clear input/output requirements ensure architectural boundaries remain intact."
  - Preference for quiet logs: "I am afraid that will lead to log bloat" — important messages get lost in noise.

## workflow-management — Kotlin + Javalin + SvelteKit SPA

- **Backend**: Kotlin, Javalin 5.6, Koin DI
- **Frontend**: SvelteKit (Svelte 5), Vite, Tailwind CSS, Melt UI, XyFlow graphs
- **Database**: PostgreSQL, Exposed ORM, HikariCP
- **Architecture**: Modular monolith with vertical slices. 12 Gradle modules (logic + sites layers).
- **Build**: Gradle, fat JAR. Frontend pre-built as static files embedded in JAR.
- **Notable**: Custom Gradle task auto-generates TypeScript types from Kotlin DTOs. SvelteKit adapter-static for pre-rendering.
- **Observations**: Extensive framework evaluation process documented. Started by asking 3 AI pairs (Claude Code + Gemini) independently — got 3 different answers (React, SvelteKit, Flutter). After cross-pollination they converged on Vue.js 3. Next day, deeper analysis revealed Vue.js lacked a native workflow designer (would need React Flow wrapper — a "frankenstack"). Final consensus: SvelteKit + Svelte Flow + Kotlin backend. Non-starters documented: Vaadin ("terrible UI and very sluggish"), Compose Multiplatform (alpha, broken JS interop). Strong preference: "Perfectly not React."
