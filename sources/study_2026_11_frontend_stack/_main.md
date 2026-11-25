https://github.com/Schinzel/stack-eval-2026

Our own study, run 2026-11-23 to 2026-11-25. The other studies in this repo compare languages. 
This one holds the backend language fixed and compares frontend approaches.

## The task

Claude Code builds the same todo app in five frontend stacks, from the same four specs, with no human at the keyboard.
The specs are stack neutral and describe behavior, not how it is built. Each stack has its own branch and starts from the same base repo.

- Backend: Go with `net/http`, the same operations layer in every stack. LiveView is the exception, it runs on Elixir with the operations layer ported
- No build step in any stack, libraries are loaded as files. Plain CSS without a framework
- Each spec is built by an implementer, checked by three reviewers and corrected by a fixer, each spec in a session of its own
- Implementer and fixer are Sonnet 5.5
- Each stack has a reference file with library versions, rules and working examples, written and tried in the browser before the run

| Spec                    | What it adds                                                        |
|-------------------------|---------------------------------------------------------------------|
| `2_todo-list`           | The todo list: add, check, rename                                   |
| `3_live-synk`           | Every change shows in all open tabs within a second, without reload |
| `4_labels-pa-todos`     | Labels on todos                                                     |
| `5_administrera-labels` | A page to administer labels                                         |

From spec 3 on, a live update must not disturb what the user is doing in another tab, such as an open field with a draft.

## What is measured

The main number is the time of the implementer plus the fixer, summed over spec 2 to 5. 
The time of the reviewers is recorded but left out, since it follows the stack little.
The quality of the code is assumed to be the same in every stack once the fixer is done. It is not measured.

## The stacks

| Stack            | Libraries                                         | Backend | Code (Group) | Who draws the UI                                     |
|------------------|---------------------------------------------------|---------|--------------|------------------------------------------------------|
| Datastar         | Datastar 1.0.5                                    | Go      | Common       | Server sends HTML, morphed into the page             |
| Preact           | Preact 11.2.0, htm 3.1.1                          | Go      | Common       | Browser. Server sends JSON                           |
| Preact and Query | Preact 11.2.0, htm 3.1.1, TanStack Query 5.108.4  | Go      | Common       | Browser. Server sends JSON                           |
| LiveView         | Phoenix 1.8.17, Phoenix LiveView 1.2.15           | Elixir  | Uncommon     | Server, over a websocket. The framework patches DOM  |
| htmx and Alpine  | htmx 2.0.11, Alpine.js 3.17.5                     | Go      | Common       | Server sends HTML fragments, swapped without morph   |

- htmx and Alpine is the frontend approach of Process Oak (Poak), the application that caused the study. Much of the development time in Poak went into the frontend
- LiveView is not a candidate. It is measured to see what happens when nearly all of the UI is built on the server
- Preact was chosen over React to avoid a build step

## Results

Implementer plus fixer over spec 2 to 5, round 2. One run per stack.

| Stack            | Implementer | Fixer  | Sum     | vs Preact |
|------------------|-------------|--------|---------|-----------|
| Preact and Query | 9m 28s      | 0m 50s | 10m 18s | 0.85      |
| Preact           | 10m 18s     | 1m 49s | 12m 7s  | 1.00      |
| LiveView         | 11m 56s     | 1m 29s | 13m 25s | 1.11      |
| htmx and Alpine  | 19m 7s      | 2m 50s | 21m 57s | 1.81      |
| Datastar         | 27m 54s     | 1m 37s | 29m 31s | 2.44      |

### Repeatability

Datastar and Preact were run twice. Round 1 ran in Docker with tools that were corrected along the way, round 2 directly on the Mac.

| Round | Datastar | Preact  | Ratio | Datastar with reviewers | Preact with reviewers | Ratio |
|-------|----------|---------|-------|-------------------------|-----------------------|-------|
| 1     | 33m 49s  | 14m 3s  | 2.4   | 51m 38s                 | 23m 55s               | 2.2   |
| 2     | 29m 31s  | 12m 7s  | 2.4   | 46m 31s                 | 21m 19s               | 2.2   |

- The same stack differs between its two runs: Preact by 1m 56s, Datastar by 4m 18s. A smaller difference between two stacks cannot be told from chance
- Preact, Preact and Query, and LiveView are therefore one group. htmx and Alpine, and Datastar, are outside chance in both directions
- A single spec in Datastar differed by up to a factor of two between the rounds. The sum over four specs is stable within ten percent

### Per spec

Implementer plus fixer, round 2.

| Spec                    | Preact and Query | Preact  | LiveView | htmx and Alpine | Datastar |
|-------------------------|------------------|---------|----------|-----------------|----------|
| `2_todo-list`           | 1m 53s           | 2m 31s  | 2m 7s    | 3m 13s          | 4m 1s    |
| `3_live-synk`           | 1m 32s           | 2m 31s  | 1m 33s   | 4m 12s          | 8m 13s   |
| `4_labels-pa-todos`     | 3m 27s           | 3m 13s  | 3m 18s   | 5m 38s          | 7m 5s    |
| `5_administrera-labels` | 3m 26s           | 3m 52s  | 6m 27s   | 8m 54s          | 10m 12s  |
| Sum                     | 10m 18s          | 12m 7s  | 13m 25s  | 21m 57s         | 29m 31s  |
| With reviewers          | 19m 55s          | 21m 19s | 22m 35s  | 36m 12s         | 46m 31s  |

- The gap grows with the spec. From spec 2 to spec 5 Preact goes from 2m 31s to 3m 52s, htmx and Alpine from 3m 13s to 8m 54s, Datastar from 4m 1s to 10m 12s
- The whole distance from LiveView to Preact and Query is in spec 5

### The implementer's work

The implementer over spec 2 to 5, round 2. Tokens, steps and calls are counted from the session logs.

| Measure                   | Preact and Query | Preact  | LiveView | htmx and Alpine | Datastar |
|---------------------------|------------------|---------|----------|-----------------|----------|
| Time                      | 9m 28s           | 10m 18s | 11m 56s  | 19m 7s          | 27m 54s  |
| Generated tokens          | 153 000          | 157 000 | 200 000  | 331 000         | 393 000  |
| Tokens per added line     | 85               | 86      | 90       | 158             | 169      |
| Steps, model responses    | 189              | 202     | 264      | 303             | 403      |
| Calls to the browser      | 62               | 75      | 97       | 117             | 142      |
| Added lines, not tests    | 1 333            | 1 380   | 1 334    | 1 596           | 1 712    |
| Added lines in tests      | 427              | 373     | 863      | 496             | 567      |

- The slow stacks do not need much more code. Datastar's code is 1.3 times the size of Preact's, but the text the model wrote on the way there is 2.5 times as large
- Nearly all the time is thinking and writing. In LiveView build and test took 41 seconds of 13m 25s. In htmx and Alpine build and test took 38 seconds and the browser 59 seconds of 19m 7s
- Time follows tokens per added line: about 85-90 in the fast group, about 160-170 in the slow stacks

### Reviewer findings

Round 2, all four specs.

| Stack            | CRITICAL | HIGH | MEDIUM | LOW |
|------------------|----------|------|--------|-----|
| Preact and Query | 0        | 2    | 12     | 25  |
| Preact           | 0        | 3    | 20     | 25  |
| LiveView         | 0        | 5    | 13     | 27  |
| htmx and Alpine  | 1        | 5    | 19     | 29  |
| Datastar         | 0        | 4    | 16     | 26  |

- Two of Preact's HIGH findings came back in both rounds, in spec 2 and 3, and were in its copy of server data in the browser. With TanStack Query they did not appear
- All CRITICAL and HIGH in htmx and Alpine were about structure, five of six about duplicated code

## Conclusions

The conclusions are an interpretation of the runs and the friction logs. The causes are not measured one by one.

Preact is the one and only owner of the UI. That is why it performs better.
There is no mix of technologies and no handover between the parts of the stack.
Preact owns everything, and the only job of the backend is to serve and receive data.

The same holds across the stacks: time follows whether the responsibility for the UI is in one place or is split between server and browser.

| Stack            | Where the responsibility for the UI is                           | Sum     |
|------------------|------------------------------------------------------------------|---------|
| Preact and Query | All in the browser. The server sends data                        | 10m 18s |
| Preact           | All in the browser. The server sends data                        | 12m 7s  |
| LiveView         | Nearly all on the server. The browser is a thin terminal         | 13m 25s |
| htmx and Alpine  | Split: the server draws HTML, Alpine and the DOM hold state      | 21m 57s |
| Datastar         | Split: the server draws HTML, signals and morph in the browser   | 29m 31s |

- That the server draws HTML is not what costs. LiveView does it and is 2.2 times faster than Datastar
- When the responsibility is split, drafts, focus and open or closed live in the DOM, outside what draws. Every response from the server becomes a merge that the app must design. In Preact the model describes state, never transitions
- Each stack fails where the responsibility is split after all: LiveView on a field with focus, Preact in its copy of server data
- That the model knows the library is not enough. htmx and Alpine are old and well known, the friction log has almost nothing about their rules, and the stack is still 1.8 times Preact
- Datastar is young and its rules had to be discovered by trying in the browser. The difference between Datastar and htmx and Alpine, 7m 34s, is the closest the runs come to a price for that
- In htmx and Alpine the implementer wrote its own morph, a file that grew from 54 lines after spec 3 to 107 after spec 5, and that gave the only CRITICAL
- Elixir is Uncommon in training data and LiveView is still in the fast group. This fits the dismissed parameter in `parameters.md`

Not settled
- Undivided responsibility and a framework that owns the merge coincide in all five stacks. htmx with idiomorph would separate them. It has not been run

## Caveats

- One run per stack, except Datastar and Preact with two
- The specs stress live sync and open fields that must not be disturbed, the case where a split costs the most. Spec 2 has no live sync, and htmx and Alpine and Datastar are the slowest there too, with smaller gaps
- Poak has no live sync. Three of four specs require it, so htmx and Alpine is measured on a requirement Poak does not have
- The app is small. Four specs on a todo list say nothing about tens of thousands of lines
- The stack reference file differs in size: 6 kB for Datastar, 10.7 kB for htmx and Alpine, 15 kB for Preact, 23 kB for Preact and Query, 27.6 kB for LiveView
- The reference file for Preact and Query pointed out the exact errors that Preact made in the earlier rounds
- Another model than Sonnet 5.5 may find Datastar easier or harder
