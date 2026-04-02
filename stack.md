# Recommended AI-Assisted Stack

Gemini's recommendation for the optimal AI-assisted stack:

## Backend
Python
- Second in benchmark (75s)
- Dynamic
- Type hints without enforcement provide scaffolding readability
- Largest library ecosystem
- Large amount of training data as a bonus
- Easiest to recruit for

## Frontend
HTML over the wire
- Declarative
- No build steps
- Minimal cognitive surface
- Clear winner

## Database type
Relational SQL
- SQL is declarative
- The schema gives the AI a clear blueprint

## Database access
Raw SQL
- Maximally explicit and buildable
- AI is good at writing SQL, bad at navigating ORMs

## Architecture
Feature-based / Vertical slices
- AI can build an entire feature in isolation without navigating directory trees

## Deployment
Monolith
- One codebase, one artifact
- Minimal cognitive overhead

## Communication
Synchronous
- Linear code flow, explicit
- Event-driven introduces implicit indirection

## Build system
Minimal/None
- Direct consequence of the other choices

## Web library
Starlette
- Python's Javalin equivalent
