# Källkandidater: språk och stack för AI-assisterad utveckling

Sammanställt 2026-09-29, kompletterat 2026-11-01. Listan innehåller möjliga källor att granska senare. Resultaten är inte tolkade. Utgångspunkten, mame/ai-coding-lang-bench (mars 2026), finns redan i `study_2026_03` och är inte med i listan.
Verifieringsstatus: **hämtad** = sidan lästes, **sökträff** = URL:en kom från sökresultat eller abstrakt och sidan lästes inte, **overifierat** = sidan gick inte att nå. **ej kontrollerad** = posten kommer från en separat sammanställning och sidan har inte kontrollerats i samband med att den lades till.

## 1. Språkjämförelser

### Hög relevans
- **The Best Programming Language for Tokenmaxxing** (Wu, Anderson, Guha) ([arXiv 2607.22807](https://arxiv.org/abs/2607.22807)). 2026-07-24. Paper. Jämför Python, Java, Rust och OCaml med 5 modeller. Mäter tokenförbrukning, hur ofta mellanlösningar kompilerar och agenternas trajektorier. Status: sökträff.
- **Do programming languages still matter to your AI coding agent teammate? Evidence at scale from chess engines** ([arXiv 2606.13763](https://arxiv.org/abs/2606.13763)). 2026-06-11. Paper. Claude Code och Codex byggde schackmotorer i 17 språk. Mäter om koden fungerar, spelstyrka, kostnad och valda features. Status: sökträff.
- **Turns, Not Lines: Token Cost of LLM Code Generation Across Seven Languages** (Sezgin) ([Zenodo](https://doi.org/10.5281/zenodo.21980217)). Augusti 2026. Rapport. En Go-modul på 2 743 rader porteras till 6 andra språk av Haiku 4.5 och Sonnet 5. Mäter tokens, turer och om porten klarar ett förbestämt beteendetest. Status: ej kontrollerad. Tillagd 2026-11-01.

### Medel relevans
- **ubershmekel/language-ai-bench** ([GitHub](https://github.com/ubershmekel/language-ai-bench)). Datum ej verifierat (v1.0). Benchmark. JS, TS strict, Python, Python+mypy strict och Go på 3 uppgiftsfamiljer, 119 rollouts. Mäter pass rate, antal steg, kostnad och om typfeedback ledde till fixar. Status: sökträff.
- **SWE-bench Multilingual** ([swebench.com](https://www.swebench.com/multilingual.html), leaderboards: [Mercor](https://www.mercor.com/apex/oss-benchmarks/oss-swe-bench-multilingual-leaderboard/), [llm-stats](https://llm-stats.com/benchmarks/swe-bench-multilingual)). 2025. Benchmark. 300 issue-uppgifter från 42 repon i 9 språk, med resultat per språk. Status: sökträff.
- **Multi-SWE-bench** ([arXiv 2504.02605](https://arxiv.org/abs/2504.02605), [leaderboard](https://multi-swe-bench.github.io/), [BenchLM](https://benchlm.ai/benchmarks/multiswebench)). April 2025, leaderboarden uppdaterad juli 2026. Benchmark/paper. 1 632 issue-uppgifter i Java, TS, JS, Go, Rust, C och C++, med % resolved per språk. Status: sökträff.
- **ABC-Bench: Agentic Backend Coding in Real-World Development** ([arXiv 2601.11077](https://arxiv.org/abs/2601.11077)). Januari 2026. Paper. Benchmark för agentisk backendkodning. Innehållet per språk eller stack är inte kontrollerat. Status: sökträff.
- **DeepSWE** ([Morph](https://www.morphllm.com/best-ai-coding-agents-2026)). 2026. Benchmark. 113 långa uppgifter i TS, Go, Python, JS och Rust. Uppgifterna kommer från en sekundärkälla. Status: sökträff.
- **Evaluating and Improving Automated Repository-Level Rust Issue Resolution with LLM-based Agents** ([arXiv 2602.22764](https://arxiv.org/html/2602.22764v1)). Februari 2026. Paper. Agenter löser issues i Rust-repon. Status: sökträff.
- **Cross-Model Cross-Language AI Coding Agent Performance** (Edelman m.fl.) ([arXiv 2607.26083](https://arxiv.org/abs/2607.26083)). Juli 2026. Paper. Parallella algoritmer i C++, Python och Julia. Status: ej kontrollerad. Tillagd 2026-11-01.

### Låg relevans
- **Aider Polyglot** (nämns i [KDnuggets](https://www.kdnuggets.com/top-10-open-source-benchmarks-for-ai-coding-agents-in-2026)). 2024–2025. Benchmark. 225 Exercism-övningar i C++, Go, Java, JS, Python och Rust som mäter modellernas redigeringsförmåga. Status: sökträff (aider.chat är inte kontrollerad).
- **Frontier Coding Agents Use Metaprogramming to Adapt to Unfamiliar Programming Languages** ([arXiv 2606.10933](https://arxiv.org/abs/2606.10933)). 2026-06-09. Paper. 6 agenter i Brainfuck och Befunge-98. Undersöker hur agenterna hanterar okända språk. Status: sökträff.
- **Which Programming Language Should You Use with Claude Code?** ([huizhou92, Medium](https://medium.huizhou92.com/which-programming-language-should-you-use-with-claude-code-39beaa4693af) och [Devrim, Stackademic](https://blog.stackademic.com/which-programming-language-should-you-use-with-claude-code-b0b7c4598969)). 2026. Bloggar som troligen kommenterar mame-benchmarken. Status: overifierat (403).
- **ClaudeLog FAQ: What programming languages work best with Claude Code** ([ClaudeLog](https://claudelog.com/faqs/what-programming-languages-work-best-with-claude-code/)). Datum okänt. Blogg, åsiktstext utan mätning. Status: sökträff.
- **LangChoiceBench** ([arXiv 2608.06041](https://arxiv.org/abs/2608.06041)). Augusti 2026. Paper från King's College London. Undersöker vilket språk modeller väljer. Status: ej kontrollerad. Tillagd 2026-11-01.
- **A Study of LLMs' Preferences for Libraries and Programming Languages** ([ACL Anthology](https://aclanthology.org/2026.findings-acl.15.pdf)). ACL Findings 2026. Paper. Undersöker vilka språk och bibliotek modeller föredrar. Status: ej kontrollerad. Tillagd 2026-11-01.

## 2. Ramverk och stacklager

### Hög relevans
- **Constraint Decay: The Fragility of LLM Agents in Backend Code Generation** ([arXiv 2605.06445](https://arxiv.org/html/2605.06445v1)). Maj 2026. Paper. 80 greenfield- och 20 feature-uppgifter i 8 backendramverk (Flask, FastAPI, Django, aiohttp, Express, Fastify, Hono, Koa). Varierar arkitekturmönster, databas och ORM och mäter assertion pass rate när kraven ökar från L0 till L3. Status: hämtad.
- **Which web frameworks are most token-efficient for AI agents?** (Martin Alderson) ([blogg](https://martinalderson.com/posts/which-web-frameworks-are-most-token-efficient-for-ai-agents/)). 2026-02-23. Blogg med egen benchmark. 19 ramverk, Claude Code + Opus 4.6, samma bloggapp plus en uppföljande funktion. Mäter tokens, tool calls, tid och om appen fungerade. Status: hämtad.
- **Vibe Coding Economically: Which Framework Is the Cheapest? (Rails vs Django vs Laravel)** ([AppSignal](https://blog.appsignal.com/2026/06/17/vibe-coding-economically-which-framework-is-the-cheapest-rails-vs-django-vs-laravel.html)). 2026-06-17. Blogg med experiment. Cursor Pro bygger samma app i tre ramverk, en körning per ramverk. Mäter tokens, tid, iterationer och N+1-frågor. Status: hämtad.
- **Architecture as Capability Equalizer for Coding Agents** ([arXiv 2608.21747](https://arxiv.org/abs/2608.21747)). Augusti 2026. Paper. 5 specformat (prosa, Mermaid+ADR, OpenAPI, C4, TS-kontrakt) × 6 modeller, 90 agentkörningar. Mäter bl.a. API-täckning. Status: sökträff.
- **From LLMs to Agents in Programming: The Impact of Providing an LLM with a Compiler** ([arXiv 2601.12146](https://arxiv.org/pdf/2601.12146)). Januari 2026. Paper. Mäter hur kompilatorfeedback påverkar LLM- och agentprestanda. Status: sökträff.
- **Type-Error Ablation and AI Coding Agents** (Krishnamurthi, Flatt) ([arXiv 2606.01522](https://arxiv.org/abs/2606.01522)). Juni 2026. Paper. Kontrollerat experiment i ett statiskt typat ML-liknande språk. Jämför typfel, testfel och felmeddelandenas utförlighet som stöd för agentens reparationer. Status: ej kontrollerad. Tillagd 2026-11-01.

### Medel relevans
- **Type-Constrained Code Generation with Language Models** ([arXiv 2504.09246](https://arxiv.org/pdf/2504.09246)). PLDI 2025. Paper. Typbegränsad avkodning i TypeScript-versioner av HumanEval och MBPP. Mäter kompileringsfel och funktionell korrekthet. Mäter avkodningsteknik, inte stackval. Status: sökträff.
- **Beyond Human-Readable: Rethinking SE Conventions for the Agentic Development Era** ([arXiv 2604.07502](https://arxiv.org/pdf/2604.07502)). 2026-04-10. Positionspapper om typsystem, namngivning och arkitektur för agenter. Sammanfattningen nämner ingen mätdata. Status: hämtad.
- **Generative Compilation: On-the-Fly Compiler Feedback as AI Generates Code** ([arXiv 2607.13921](https://arxiv.org/pdf/2607.13921)). Juli 2026. Paper. Kompilatorfeedback medan koden genereras. Status: sökträff.
- **Web-Bench** ([arXiv 2505.07473](https://arxiv.org/abs/2505.07473)). Maj 2025. Benchmark/paper. Sekventiella projektuppgifter över webbstandarder och webbramverk, mätt med Pass@1. Status: sökträff.
- **We let AI coding agents into our codebase. The modular monolith won.** ([dev.to](https://dev.to/thien_nguyen/we-let-ai-coding-agents-into-our-codebase-the-modular-monolith-won-50je)). 2026-06-30. Blogg, erfarenhetsrapport utan mätdata. Status: hämtad.
- **Do AI Coding Agents Reason Better in Modular Monoliths Than Microservices?** (Vishal Mysore) ([Medium](https://medium.com/@visrow/do-ai-coding-agents-reason-better-in-modular-monoliths-than-microservices-b2549e1c1ab3)). Maj 2026. Blogg. Status: sökträff.
- **Modular Monolith Instead of Microservices — What Changed When the AI Agent Started Reading Code** (Jaroslaw Wasowski) ([Medium](https://medium.com/@wasowski.jarek/modular-monolith-instead-of-microservices-what-changed-when-the-ai-agent-started-reading-code-c586d9f63fd7)). Maj 2026. Blogg, erfarenhetsrapport. Status: sökträff.
- **The Codebase Is the Prompt: Wolverine, Vertical Slices, and AI-Assisted Development** (Jeremy D. Miller) ([blogg](https://jeremydmiller.com/2026/06/04/the-codebase-is-the-prompt-wolverine-vertical-slices-and-ai-assisted-development/)). 2026-06-04. Blogg av en ramverksförfattare, erfarenhetsrapport om vertikala slices. Status: sökträff.

### Låg relevans
- **Keep the AI Vibe: Optimizing Codebase Architecture for AI Coding Tools** (Rick Hightower) ([Medium](https://medium.com/@richardhightower/ai-optimizing-codebase-architecture-for-ai-coding-tools-ff6bb6fdc497)). Blogg, opinion. Status: sökträff.
- **WebGen-Bench** ([arXiv 2505.03733](https://arxiv.org/html/2505.03733v2)). 2025. Benchmark. Agenter bygger webbplatser med flera filer från grunden. Status: sökträff.
- **AgenticTyper: Automated Typing of Legacy Software Projects Using Agentic AI** ([arXiv 2602.21251](https://arxiv.org/pdf/2602.21251)). 2026-02-26. Paper. Agenter lägger till typer i JS/TS-kod. Status: hämtad.
- **Automated Type Annotation in Python Using LLMs** ([arXiv 2508.00422](https://arxiv.org/abs/2508.00422)). Augusti 2025. Paper. En loop som genererar typannotationer, kontrollerar dem med mypy och reparerar på ManyTypes4Py. Status: sökträff.
- **TypyBench** ([arXiv 2507.22086](https://arxiv.org/pdf/2507.22086)). 2025. Benchmark för typinferens i otypade Python-repon. Status: sökträff.
- **Why 94% of AI Code Errors Are Pushing Us All Toward TypeScript** ([YUV.AI](https://yuv.ai/blog/why-94-of-ai-code-errors-are-pushing-us-all-toward-typescript)). Blogg. Siffran tillskrivs Octoverse 2025, men attribueringen är inte kontrollerad. Status: sökträff.
- **ProcArena** ([arXiv 2609.06527](https://arxiv.org/pdf/2609.06527)). September 2026. Paper. LLM:er som utvecklar PL/SQL. Status: sökträff.
- **Prisma Schema as LLM Context: Why Agents Read It Best** ([Prisma](https://www.prisma.io/blog/prisma-schema-as-llm-context)). Blogg från en leverantör. Status: sökträff.
- **Using AI to Generate Database Query Is Cool. But What About Access Control?** ([ZenStack](https://zenstack.dev/blog/llm-acl)). Blogg om Prisma-frågor och SQL för LLM:er. Status: sökträff.
- **Best Frameworks for AI-Assisted Development 2026** ([Encore.dev](https://encore.dev/articles/best-frameworks-ai-assisted-development)). 2026. Blogg från en leverantör, utan mätning. Status: sökträff.
- **Rails and AI** ([rubyonrails.org](https://rubyonrails.org/ai)). Ramverkets egen sida. Status: sökträff.
- **htmx-claude-skill** ([GitHub](https://github.com/ercan-er/htmx-claude-skill)). En skill som styr agenter mot HTML-over-the-wire. Ingen mätning. Status: sökträff.
- **Javascript Fatigue? Build an Agentic Chatbot with HTMX** ([Medium](https://medium.com/data-science-collective/javascript-fatigued-build-an-agentic-chatbot-with-htmx-503569adf2f9)). December 2025. Blogg. Status: sökträff.

## 3. Akademiska papper (generella och flerspråkiga benchmarks)

Notera: alla källor i denna grupp bedömdes utifrån titel, abstrakt eller sökutdrag. Ingen fulltext lästes.

### Medel relevans
- **AutoCodeBench** ([arXiv 2508.09101](https://arxiv.org/abs/2508.09101)). Augusti 2025. Paper. 3 920 problem över 20 språk, 30+ modeller, med Pass@1 per språk. Status: sökträff.
- **CRUXEVAL-X** ([DOI](https://doi.org/10.18653/v1/2025.acl-long.1158)). ACL 2025. Paper. Benchmark för kodresonemang och exekvering i många språk. Status: sökträff.
- **A Survey on LLM-based Code Generation for Low-Resource and Domain-Specific Programming Languages** ([DOI](https://doi.org/10.1145/3770084)). ACM TOSEM 2025. Översikt om prestandagapet mellan hög- och lågresursspråk. Status: sökträff.
- **Enhancing Code Generation for Low-Resource Languages: No Silver Bullet** ([arXiv 2501.19085](https://arxiv.org/abs/2501.19085)). ICPC 2025. Paper. Jämför tekniker för LLM-kod i lågresursspråk. Status: sökträff.
- **SWE-Bench ProMax** ([arXiv 2608.09802](https://arxiv.org/pdf/2608.09802)). Augusti 2026. Paper. Agenter gör storskalig refaktorering i flera språk. Endast titeln är sedd. Status: sökträff.
- **Security and Quality in LLM-Generated Code: A Multi-Language, Multi-Model Analysis** ([arXiv 2502.01853](https://arxiv.org/html/2502.01853v1)). Februari 2025. Paper. Säkerhet och kvalitet i genererad kod i flera språk. Status: sökträff.
- **Evaluation of LLMs on Syntax-Aware Code Fill-in-the-Middle Tasks** ([arXiv 2403.04814](https://arxiv.org/pdf/2403.04814)). 2024, utanför tidsramen. Paper. Fill-in-the-middle-uppgifter i flera språk, med resultat per språk. Status: sökträff.

### Låg relevans
- **EffiBench-X** ([arXiv 2505.13004](https://arxiv.org/pdf/2505.13004)). NeurIPS 2025. Paper. Körtid och minne för LLM-genererad kod i flera språk. Status: sökträff.
- **No Resource, No Benchmarks, No Problem?** ([arXiv 2606.16827](https://arxiv.org/abs/2606.16827)). IEEE TSE 2026. Paper. LLM-kodgenerering i språk utan träningsdata. Status: sökträff.
- **CangjieBench** ([arXiv 2603.14501](https://arxiv.org/abs/2603.14501)). Mars 2026. Benchmark för lågresursspråket Cangjie. Status: sökträff.
- **Position Paper: PL Techniques for Bridging LLM Code Generation Semantic Gaps** ([arXiv 2507.09135](https://arxiv.org/html/2507.09135v1)). 2025. Positionspapper utan mätningar. Status: sökträff.

## Luckor
- Inga mätande jämförelser av Next.js mot Rails eller Laravel med success rate. Alderson mäter bara tokens.
- Inga kontrollerade agentexperiment för TS mot JS eller för Python med och utan mypy, utöver ubershmekel och mame (overhead för mypy och Steep).
- Inga agentexperiment för SQL mot NoSQL. Ren SQL mot ORM finns bara som en dimension i Constraint Decay.
- Inga benchmarks för HTMX eller servergenererad HTML mot SPA.
- Inga kontrollerade mätningar av monolit mot mikrotjänster eller av vertikala slices mot lager.
- Inga studier som isolerar byggverktygens komplexitet (Vite/webpack, monorepo).
- Ingen studie från 2025–2026 som regresserar agentframgång mot språkegenskaper (typsystem, verbositet, paradigm, mängd träningsdata).
- Inga blogginlägg utöver mame, kmizu och Dan Luu där samma app byggts i flera språk med mätning.
- Ej kontrollerat: om mame-repot uppdaterats efter mars 2026, forkarna i övrigt (68 st), publiceringsdatum för Dan Luus inlägg, och om Terminal-Bench redovisar resultat per språk.
- Resultat per språk från Multi-SWE-bench, SWE-bench Multilingual och AutoCodeBench med modeller från 2026 har inte hämtats.
