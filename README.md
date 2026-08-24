# ERP Upgrade Assistant

ERP Upgrade Assistant is a small architecture case study for reducing repetitive manual work when preparing ERP upgrades.

The solution validates upgrade characteristics, applies deterministic compatibility rules, selects a target version, maps it to upgrade artifacts, and generates a recommendation. A consultant reviews and approves the result before it is used.

## Main Flow

`Current Version -> Upgrade Characteristics -> Compatibility Rules -> Target Version -> Artifact Catalog -> Recommendation -> Consultant Approval`

The assistant supports the consultant; it does not execute an upgrade or replace consultant responsibility.

## Status

Initial Architecture / Concept - **IN PROGRESS**. This repository documents a proposed solution, not a production implementation.

## Documentation

- [Problem and Goals](docs/01-problem-and-goals.md)
- [Scope](docs/02-scope.md)
- [Process](docs/03-process.md)
- [Architecture](docs/04-architecture.md)
- [Security and Constraints](docs/05-security-and-constraints.md)
- [ADR-001](docs/adr/ADR-001-rules-based-automation.md)
- [Project Status](PROJECT_STATUS.md)
- [Open Questions](OPEN_QUESTIONS.md)
