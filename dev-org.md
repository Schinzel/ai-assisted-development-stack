# Purpose

The purpose of this document is to establish what an ideal product development department looks like today.


## Today's workflow
Today's workflow typically looks as follows:

- Product owner
- Designer
- 2-8 developers
- Possibly tester



## Why we need to change the workflow
Today large language models 
- write all the code. As such. the output each developer is much higher with proper user of LLMs.
- can can do a large part of the design work.
- can write automated tests

## What the workflow should be

- The technical people are more system designers or architects than they are code writers. 
- QA/Testing should be automatic tests. 
- The work of the designer is changed from producing things in the workflow to creating and maintaining a design system, which is used by the large language models in the workflow. If a feature has difficult of fundamental UI aspects, the designer can do work in the workflow.

Cross team
- Architect
- Designer

Per product or area
- 1 Product owner
- 1 or 2 Developers / system-designers

If a feature has technical work of significance, the architect could approve it. 

## Code reviews & Scaffolding
The development process for developers is changed to
- **Problem Discovery** - Discuss the problem with an LLM which create a task document
- **Architectural Blueprint** - Ask LLM to scaffold the task
- **Human Gatekeeper** - LLM and developer discusses the scaffolding and makes adjustments. 
- The task document and the scaffolded files acts as input to the agentic workflow where a series of agents produces the code
- Human review of code


Why scaffolding
- The developer can much easier review 200 lines of scaffolded code than 2000 lines of actual code
- If is the correct level of detail. The humans should focus on the design of the system, not lines of code
- Also, it is much faster for the LLM to do changes in scaffolded files, creating a fast iterative process for system design
- It is more expensive - in tokens spent - to make the same changes in fully implemented code

A strong case can be made for that the more important code review by another human is the scaffolded file. 
- It is in the system design the expensive mistakes are made
- The volume of code in the code reviews can turn it into a linting exercise, more than an audit of system design

## Constant state of change
The bottleneck is no longer coding, but our ability to evolve our processes.
A development organization should be in a constant state of continuous small improvements.
One can always be better, and we should in the sprit of kaizen strive continuous improvements
Also, circumstance change: teams change, the product changes, the demands change.
One should acknowledge this and adapt to these changing circumstance.
This above always important, but is much more important in this age of AI assisted development. 
This as the ground under our feet change at a dramatic pace. 
What is true yesterday is not true today and what is true today in not true tomorrow. 
An organization that embraces this will handle this age AI assisted development much better than those that do not. 
