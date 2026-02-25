# biosciences-evaluation

Evaluation rubrics, quality metrics, and testing standards for the Open Biosciences platform.

Part of the [Open Biosciences](https://github.com/open-biosciences) multi-repo platform.

## Status

**Wave 4 (Validation) — migration pending.** This repository is a target for Wave 4 of the platform migration. Content will be populated once Waves 1-3 (Foundation, Platform, Orchestration) are complete.

## What Will Be Here

- Evaluation rubrics for MCP server quality, agent performance, and research output accuracy
- Quality metrics definitions (test coverage thresholds, API response accuracy, knowledge graph completeness)
- Cross-repo test quality standards and enforcement gates

This repo serves as a **quality gate layer** — it reads from all other repos but no repo depends on it. It provides observability and accountability without introducing coupling.

## Owner

Quality & Skills Engineer agent (also owns `biosciences-skills`).

## Dependencies

| Dependency | Relationship |
|-----------|-------------|
| All platform repos | Reads metrics and test results from each |

## Related Repos

- [biosciences-skills](https://github.com/open-biosciences/biosciences-skills) — Domain skills and SpecKit commands (same owner)
- [biosciences-mcp](https://github.com/open-biosciences/biosciences-mcp) — MCP servers evaluated for quality
- [biosciences-architecture](https://github.com/open-biosciences/biosciences-architecture) — ADRs and standards this repo enforces

## License

MIT
