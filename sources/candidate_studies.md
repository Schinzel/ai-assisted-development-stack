# Source candidates: language and stack for AI-assisted development

## Purpose
The purpose of this file is to be the queue of sources that may become studies in this repo. It keeps the search work so it does not have to be redone, and the Gaps section records what we looked for and did not find. When a source is turned into a study, it gets its own folder under `sources/` and is removed from the list.

## History
Compiled 2026-09-29, supplemented 2026-11-01. The list contains possible sources to review later. The results have not been interpreted. Three sources have their own study folders and are therefore not included in the list:
- mame/ai-coding-lang-bench (March 2026), the starting point: [study_2026_03_mini_git](study_2026_03_mini_git/_main.md)
- kmizu/another-ai-coding-lang-bench: [study_2026_03_mini_git_2](study_2026_03_mini_git_2/_main.md)
- Dan Luu's post on token efficiency and correctness: [study_2026_zstd](study_2026_zstd/_main.md)

Verification status: **fetched** = the page was read, **search hit** = the URL came from search results or an abstract and the page was not read, **unverified** = the page could not be reached. **not checked** = the entry comes from a separate compilation and the page was not checked when the entry was added.

## 1. Language comparisons

### High relevance
- **The Best Programming Language for Tokenmaxxing** (Wu, Anderson, Guha) ([arXiv 2607.22807](https://arxiv.org/abs/2607.22807)). 2026-07-24. Paper. Compares Python, Java, Rust and OCaml with 5 models. Measures token usage, how often intermediate solutions compile, and the agents' trajectories. Status: search hit.
- **Do programming languages still matter to your AI coding agent teammate? Evidence at scale from chess engines** ([arXiv 2606.13763](https://arxiv.org/abs/2606.13763)). 2026-06-11. Paper. Claude Code and Codex built chess engines in 17 languages. Measures whether the code works, playing strength, cost and the features chosen. Status: search hit.
- **Turns, Not Lines: Token Cost of LLM Code Generation Across Seven Languages** (Sezgin) ([Zenodo](https://doi.org/10.5281/zenodo.21980217)). August 2026. Report. A 2,743-line Go module is ported to 6 other languages by Haiku 4.5 and Sonnet 5. Measures tokens, turns and whether the port passes a predetermined behavior test. Status: not checked. Added 2026-11-01.

### Medium relevance
- **ubershmekel/language-ai-bench** ([GitHub](https://github.com/ubershmekel/language-ai-bench)). Date not verified (v1.0). Benchmark. JS, TS strict, Python, Python+mypy strict and Go on 3 task families, 119 rollouts. Measures pass rate, number of steps, cost and whether type feedback led to fixes. Status: search hit.
- **SWE-bench Multilingual** ([swebench.com](https://www.swebench.com/multilingual.html), leaderboards: [Mercor](https://www.mercor.com/apex/oss-benchmarks/oss-swe-bench-multilingual-leaderboard/), [llm-stats](https://llm-stats.com/benchmarks/swe-bench-multilingual)). 2025. Benchmark. 300 issue tasks from 42 repos in 9 languages, with per-language results. Status: search hit.
- **Multi-SWE-bench** ([arXiv 2504.02605](https://arxiv.org/abs/2504.02605), [leaderboard](https://multi-swe-bench.github.io/), [BenchLM](https://benchlm.ai/benchmarks/multiswebench)). April 2025, leaderboard updated July 2026. Benchmark/paper. 1,632 issue tasks in Java, TS, JS, Go, Rust, C and C++, with % resolved per language. Status: search hit.
- **ABC-Bench: Agentic Backend Coding in Real-World Development** ([arXiv 2601.11077](https://arxiv.org/abs/2601.11077)). January 2026. Paper. Benchmark for agentic backend coding. Per-language or per-stack content not checked. Status: search hit.
- **DeepSWE** ([Morph](https://www.morphllm.com/best-ai-coding-agents-2026)). 2026. Benchmark. 113 long tasks in TS, Go, Python, JS and Rust. The task details come from a secondary source. Status: search hit.
- **Evaluating and Improving Automated Repository-Level Rust Issue Resolution with LLM-based Agents** ([arXiv 2602.22764](https://arxiv.org/html/2602.22764v1)). February 2026. Paper. Agents resolve issues in Rust repos. Status: search hit.
- **Cross-Model Cross-Language AI Coding Agent Performance** (Edelman et al.) ([arXiv 2607.26083](https://arxiv.org/abs/2607.26083)). July 2026. Paper. Parallel algorithms in C++, Python and Julia. Status: not checked. Added 2026-11-01.

### Low relevance
- **Aider Polyglot** (mentioned in [KDnuggets](https://www.kdnuggets.com/top-10-open-source-benchmarks-for-ai-coding-agents-in-2026)). 2024–2025. Benchmark. 225 Exercism exercises in C++, Go, Java, JS, Python and Rust that measure the models' editing ability. Status: search hit (aider.chat not checked).
- **Frontier Coding Agents Use Metaprogramming to Adapt to Unfamiliar Programming Languages** ([arXiv 2606.10933](https://arxiv.org/abs/2606.10933)). 2026-06-09. Paper. 6 agents in Brainfuck and Befunge-98. Examines how agents handle unfamiliar languages. Status: search hit.
- **Which Programming Language Should You Use with Claude Code?** ([huizhou92, Medium](https://medium.huizhou92.com/which-programming-language-should-you-use-with-claude-code-39beaa4693af) and [Devrim, Stackademic](https://blog.stackademic.com/which-programming-language-should-you-use-with-claude-code-b0b7c4598969)). 2026. Blog posts that probably comment on the mame benchmark. Status: unverified (403).
- **ClaudeLog FAQ: What programming languages work best with Claude Code** ([ClaudeLog](https://claudelog.com/faqs/what-programming-languages-work-best-with-claude-code/)). Date unknown. Blog, opinion piece without measurements. Status: search hit.
- **LangChoiceBench** ([arXiv 2608.06041](https://arxiv.org/abs/2608.06041)). August 2026. Paper from King's College London. Examines which programming language the models choose. Status: not checked. Added 2026-11-01.
- **A Study of LLMs' Preferences for Libraries and Programming Languages** ([ACL Anthology](https://aclanthology.org/2026.findings-acl.15.pdf)). ACL Findings 2026. Paper. Examines which languages and libraries models prefer. Status: not checked. Added 2026-11-01.

## 2. Frameworks and stack layers

### High relevance
- **Constraint Decay: The Fragility of LLM Agents in Backend Code Generation** ([arXiv 2605.06445](https://arxiv.org/html/2605.06445v1)). May 2026. Paper. 80 greenfield and 20 feature tasks in 8 backend frameworks (Flask, FastAPI, Django, aiohttp, Express, Fastify, Hono, Koa). Varies architecture pattern, database and ORM, and measures assertion pass rate as requirements increase from L0 to L3. Status: fetched.
- **Which web frameworks are most token-efficient for AI agents?** (Martin Alderson) ([blog](https://martinalderson.com/posts/which-web-frameworks-are-most-token-efficient-for-ai-agents/)). 2026-02-23. Blog with its own benchmark. 19 frameworks, Claude Code + Opus 4.6, the same blog app plus a follow-up feature. Measures tokens, tool calls, time and whether the app worked. Status: fetched.
- **Vibe Coding Economically: Which Framework Is the Cheapest? (Rails vs Django vs Laravel)** ([AppSignal](https://blog.appsignal.com/2026/06/17/vibe-coding-economically-which-framework-is-the-cheapest-rails-vs-django-vs-laravel.html)). 2026-06-17. Blog with an experiment. Cursor Pro builds the same app in three frameworks, one run per framework. Measures tokens, time, iterations and N+1 queries. Status: fetched.
- **Architecture as Capability Equalizer for Coding Agents** ([arXiv 2608.21747](https://arxiv.org/abs/2608.21747)). August 2026. Paper. 5 spec formats (prose, Mermaid+ADR, OpenAPI, C4, TS contracts) × 6 models, 90 agent runs. Measures, among other things, API coverage. Status: search hit.
- **From LLMs to Agents in Programming: The Impact of Providing an LLM with a Compiler** ([arXiv 2601.12146](https://arxiv.org/pdf/2601.12146)). January 2026. Paper. Measures how compiler feedback affects LLM and agent performance. Status: search hit.
- **Type-Error Ablation and AI Coding Agents** (Krishnamurthi, Flatt) ([arXiv 2606.01522](https://arxiv.org/abs/2606.01522)). June 2026. Paper. Controlled experiment in a statically typed ML-like language. Compares type errors, test failures and the verbosity of error messages as support for the agent's repairs. Status: not checked. Added 2026-11-01.

### Medium relevance
- **Type-Constrained Code Generation with Language Models** ([arXiv 2504.09246](https://arxiv.org/pdf/2504.09246)). PLDI 2025. Paper. Type-constrained decoding on TypeScript versions of HumanEval and MBPP. Measures compilation errors and functional correctness. Measures a decoding technique, not stack choice. Status: search hit.
- **Beyond Human-Readable: Rethinking SE Conventions for the Agentic Development Era** ([arXiv 2604.07502](https://arxiv.org/pdf/2604.07502)). 2026-04-10. Position paper on type systems, naming and architecture for agents. The abstract mentions no measurement data. Status: fetched.
- **Generative Compilation: On-the-Fly Compiler Feedback as AI Generates Code** ([arXiv 2607.13921](https://arxiv.org/pdf/2607.13921)). July 2026. Paper. Compiler feedback while code is being generated. Status: search hit.
- **Web-Bench** ([arXiv 2505.07473](https://arxiv.org/abs/2505.07473)). May 2025. Benchmark/paper. Sequential project tasks across web standards and web frameworks, measured with Pass@1. Status: search hit.
- **We let AI coding agents into our codebase. The modular monolith won.** ([dev.to](https://dev.to/thien_nguyen/we-let-ai-coding-agents-into-our-codebase-the-modular-monolith-won-50je)). 2026-06-30. Blog, experience report without measurement data. Status: fetched.
- **Do AI Coding Agents Reason Better in Modular Monoliths Than Microservices?** (Vishal Mysore) ([Medium](https://medium.com/@visrow/do-ai-coding-agents-reason-better-in-modular-monoliths-than-microservices-b2549e1c1ab3)). May 2026. Blog. Status: search hit.
- **Modular Monolith Instead of Microservices — What Changed When the AI Agent Started Reading Code** (Jaroslaw Wasowski) ([Medium](https://medium.com/@wasowski.jarek/modular-monolith-instead-of-microservices-what-changed-when-the-ai-agent-started-reading-code-c586d9f63fd7)). May 2026. Blog, experience report. Status: search hit.
- **The Codebase Is the Prompt: Wolverine, Vertical Slices, and AI-Assisted Development** (Jeremy D. Miller) ([blog](https://jeremydmiller.com/2026/06/04/the-codebase-is-the-prompt-wolverine-vertical-slices-and-ai-assisted-development/)). 2026-06-04. Blog by a framework author, experience report on vertical slices. Status: search hit.

### Low relevance
- **Keep the AI Vibe: Optimizing Codebase Architecture for AI Coding Tools** (Rick Hightower) ([Medium](https://medium.com/@richardhightower/ai-optimizing-codebase-architecture-for-ai-coding-tools-ff6bb6fdc497)). Blog, opinion. Status: search hit.
- **WebGen-Bench** ([arXiv 2505.03733](https://arxiv.org/html/2505.03733v2)). 2025. Benchmark. Agents build multi-file websites from scratch. Status: search hit.
- **AgenticTyper: Automated Typing of Legacy Software Projects Using Agentic AI** ([arXiv 2602.21251](https://arxiv.org/pdf/2602.21251)). 2026-02-26. Paper. Agents add types to JS/TS code. Status: fetched.
- **Automated Type Annotation in Python Using LLMs** ([arXiv 2508.00422](https://arxiv.org/abs/2508.00422)). August 2025. Paper. A loop that generates type annotations, checks them with mypy and repairs them, on ManyTypes4Py. Status: search hit.
- **TypyBench** ([arXiv 2507.22086](https://arxiv.org/pdf/2507.22086)). 2025. Benchmark for type inference in untyped Python repos. Status: search hit.
- **Why 94% of AI Code Errors Are Pushing Us All Toward TypeScript** ([YUV.AI](https://yuv.ai/blog/why-94-of-ai-code-errors-are-pushing-us-all-toward-typescript)). Blog. The figure is attributed to Octoverse 2025, but the attribution has not been checked. Status: search hit.
- **ProcArena** ([arXiv 2609.06527](https://arxiv.org/pdf/2609.06527)). September 2026. Paper. LLMs developing PL/SQL. Status: search hit.
- **Prisma Schema as LLM Context: Why Agents Read It Best** ([Prisma](https://www.prisma.io/blog/prisma-schema-as-llm-context)). Vendor blog. Status: search hit.
- **Using AI to Generate Database Query Is Cool. But What About Access Control?** ([ZenStack](https://zenstack.dev/blog/llm-acl)). Blog on Prisma queries and SQL for LLMs. Status: search hit.
- **Best Frameworks for AI-Assisted Development 2026** ([Encore.dev](https://encore.dev/articles/best-frameworks-ai-assisted-development)). 2026. Vendor blog, without measurements. Status: search hit.
- **Rails and AI** ([rubyonrails.org](https://rubyonrails.org/ai)). The framework's own page. Status: search hit.
- **htmx-claude-skill** ([GitHub](https://github.com/ercan-er/htmx-claude-skill)). A skill that steers agents toward HTML-over-the-wire. No measurements. Status: search hit.
- **Javascript Fatigue? Build an Agentic Chatbot with HTMX** ([Medium](https://medium.com/data-science-collective/javascript-fatigued-build-an-agentic-chatbot-with-htmx-503569adf2f9)). December 2025. Blog. Status: search hit.

## 3. Academic papers (general and multilingual benchmarks)

Note: all sources in this group were assessed from title, abstract or search snippet. No full text was read.

### Medium relevance
- **AutoCodeBench** ([arXiv 2508.09101](https://arxiv.org/abs/2508.09101)). August 2025. Paper. 3,920 problems across 20 languages, 30+ models, with Pass@1 per language. Status: search hit.
- **CRUXEVAL-X** ([DOI](https://doi.org/10.18653/v1/2025.acl-long.1158)). ACL 2025. Paper. Benchmark for code reasoning and execution in many languages. Status: search hit.
- **A Survey on LLM-based Code Generation for Low-Resource and Domain-Specific Programming Languages** ([DOI](https://doi.org/10.1145/3770084)). ACM TOSEM 2025. Survey of the performance gap between high- and low-resource languages. Status: search hit.
- **Enhancing Code Generation for Low-Resource Languages: No Silver Bullet** ([arXiv 2501.19085](https://arxiv.org/abs/2501.19085)). ICPC 2025. Paper. Compares techniques for LLM code in low-resource languages. Status: search hit.
- **SWE-Bench ProMax** ([arXiv 2608.09802](https://arxiv.org/pdf/2608.09802)). August 2026. Paper. Agents perform large-scale refactoring in several languages. Only the title has been seen. Status: search hit.
- **Security and Quality in LLM-Generated Code: A Multi-Language, Multi-Model Analysis** ([arXiv 2502.01853](https://arxiv.org/html/2502.01853v1)). February 2025. Paper. Security and quality of generated code in several languages. Status: search hit.
- **Evaluation of LLMs on Syntax-Aware Code Fill-in-the-Middle Tasks** ([arXiv 2403.04814](https://arxiv.org/pdf/2403.04814)). 2024, outside the time frame. Paper. Fill-in-the-middle tasks in several languages, with per-language results. Status: search hit.

### Low relevance
- **EffiBench-X** ([arXiv 2505.13004](https://arxiv.org/pdf/2505.13004)). NeurIPS 2025. Paper. Runtime and memory of LLM-generated code in several languages. Status: search hit.
- **No Resource, No Benchmarks, No Problem?** ([arXiv 2606.16827](https://arxiv.org/abs/2606.16827)). IEEE TSE 2026. Paper. LLM code generation in languages with no training data. Status: search hit.
- **CangjieBench** ([arXiv 2603.14501](https://arxiv.org/abs/2603.14501)). March 2026. Benchmark for the low-resource language Cangjie. Status: search hit.
- **Position Paper: PL Techniques for Bridging LLM Code Generation Semantic Gaps** ([arXiv 2507.09135](https://arxiv.org/html/2507.09135v1)). 2025. Position paper without measurements. Status: search hit.

## Gaps
- No measured comparisons of Next.js versus Rails or Laravel by success rate. Alderson only measures tokens.
- No controlled agent experiments on TS versus JS or on Python with and without mypy, beyond ubershmekel and mame (overhead for mypy and Steep).
- No agent experiments on SQL versus NoSQL. Raw SQL versus ORM exists only as one dimension in Constraint Decay.
- No benchmarks for HTMX or server-rendered HTML versus SPA.
- No controlled measurements of monolith versus microservices, or of vertical slices versus layers.
- No studies isolating build tooling complexity (Vite/webpack, monorepo).
- No 2025–2026 study that regresses agent success against language properties (type system, verbosity, paradigm, amount of training data).
- No blog posts beyond mame, kmizu and Dan Luu (all three have their own study folders, see the top of this file) where the same app was built in several languages with measurements.
- Not checked: whether the mame repo has been updated after March 2026, the other forks (68 in total), the publication date of Dan Luu's post, and whether Terminal-Bench reports per-language results.
- Per-language results from Multi-SWE-bench, SWE-bench Multilingual and AutoCodeBench with 2026 models have not been fetched.
