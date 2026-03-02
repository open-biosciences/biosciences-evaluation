# biosciences-evaluation

Quality gate layer for the Open Biosciences platform. Defines evaluation rubrics, quality metrics,
and cross-repo standards that hold all platform components accountable — without introducing coupling.

Part of the [Open Biosciences](https://github.com/open-biosciences) multi-repo platform.

## Status

**Wave 4 (Validation) — Not Started.** This repository will receive new content (not migrated from
a predecessor repo) once Waves 2 and 3 are complete and operational agents exist to measure.

- Waves 1 + 2 (Foundation + Platform): Complete
- Wave 3 (Orchestration): Complete
- Wave 4 (Validation): Not Started — prerequisite: Waves 2 + 3

## Role

`biosciences-evaluation` is the **quality gate layer** of the platform. It reads from all other
repos but no repo depends on it. This design provides observability and accountability without
introducing coupling: any repo can evolve independently; evaluation simply re-measures.

## What Will Be Here (Wave 4)

### Evaluation Rubrics

Three measurement dimensions covering the full platform stack:

| Dimension | What It Measures |
|-----------|-----------------|
| MCP server quality | Response accuracy, identifier resolution fidelity (CURIE correctness), error handling coverage |
| Agent performance | Phase completion rates, hallucination detection, CURIE resolution accuracy across LangGraph and Temporal agents |
| Research output accuracy | Knowledge graph completeness, cross-source consistency, provenance traceability |

### Quality Metrics Definitions

Concrete thresholds and benchmarks applied across all repos:

- **Test coverage**: per-server minimums (unit coverage ≥80% for new code)
- **API response accuracy**: benchmarks for each of the 12 MCP servers
- **Knowledge graph completeness**: standards for entity and relationship coverage

### Cross-Repo Standards and Enforcement Gates

- Ruff + pyright clean on all Python files
- Integration test required for every MCP server tool
- ADR compliance verified for schema changes
- pytest marker discipline: `unit`, `integration`, `e2e`

## Owner

**Quality & Skills Engineer (Agent 8)** — also owns
[biosciences-skills](https://github.com/open-biosciences/biosciences-skills).

## Dependency Direction

| Relationship | Direction |
|-------------|-----------|
| All platform repos | This repo reads from them; they do not depend on it |

This repo has no upstream code dependencies. It is a consumer, not a provider.

## Related Repos

- [biosciences-skills](https://github.com/open-biosciences/biosciences-skills) — Domain skills and SpecKit commands (same owner)
- [biosciences-mcp](https://github.com/open-biosciences/biosciences-mcp) — Primary subject of MCP quality rubrics (12 FastMCP servers, 697+ tests)
- [biosciences-program](https://github.com/open-biosciences/biosciences-program) — ADRs, governance, and platform standards this repo enforces

## License

MIT
