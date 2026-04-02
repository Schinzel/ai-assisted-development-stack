# Architecture

## Layered / N-tier
Horizontal layers: presentation → logic → data

## Feature-based / Vertical slices
Organized per feature, each slice has its own presentation, logic, data

## Onion / Clean Architecture
Concentric layers with the domain at the center, dependencies point inward

## Hexagonal / Ports & Adapters
Domain logic at the core, the outside world connects via defined ports

## CQRS
Separate models and paths for reads vs writes

## Flat / Script-style
No formal structure, files organized ad hoc

# Ranked against our 10 parameters

## 1. Feature-based / Vertical slices
Best overall.
- Explicit (everything for a feature in one place)
- Thin (minimal ceremony)
- Small cognitive surface (focus on one feature at a time)
- Extremely buildable (AI can create an entire feature in isolation without navigating)
- Readable — related code is co-located
- Downside: can become inconsistent between features

## 2. Flat / Script-style
Second for small scale.
- Maximally thin, no indirections, nothing to learn
- AI just writes code
- But falls apart entirely at larger codebases — no separation, no structure to reason about

## 3. Layered / N-tier
Medium.
- Orthogonal layers (that's the whole point)
- But code for a feature is spread across three-four directories
- AI must navigate: "where do I put this?"
- Breaks buildable, not navigable

## 4. CQRS
Medium-low.
- Clear separation of reads/writes
- But doubles cognitive surface — two models to keep in mind
- Justified in specific domains but breaks thinness and small cognitive surface

## 5. Hexagonal / Ports & Adapters
Low.
- Ports, adapters, interfaces, dependency inversion
- Lots of ceremony, lots of navigation
- AI must understand the pattern before it can build

## 6. Onion / Clean Architecture
Worst.
- Entities, use cases, interfaces, DTOs, mappers — a simple feature requires five-six files
- Maximally navigable, minimal buildability
- Exactly the kind of labyrinth AI performs poorly in
