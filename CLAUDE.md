# CLAUDE.md — biosciences-evaluation

## Purpose

Evaluation framework, quality metrics, and benchmarking for the Open Biosciences platform. This repo is co-owned by the **Quality & Skills Engineer** agent.

## Responsibilities

- Define evaluation rubrics for each competency question
- Establish quality metrics and baselines
- Cross-repo test coverage analysis
- Agent output quality scoring

## Directory Structure (post-migration)

```
biosciences-evaluation/
├── rubrics/                # Evaluation rubrics per CQ
│   ├── cq14-rubric.md
│   └── ...
├── metrics/                # Quality metric definitions
│   ├── accuracy.md
│   ├── completeness.md
│   └── provenance.md
└── reports/                # Evaluation run outputs
```

## Evaluation Dimensions

| Dimension | What It Measures |
|-----------|-----------------|
| **Accuracy** | Are CURIE resolutions correct? Do cross-references match? |
| **Completeness** | Did the agent find all relevant entities and relationships? |
| **Provenance** | Can every claim be traced to a source database? |
| **Latency** | Time to complete each workflow phase |
| **Token Efficiency** | Token usage per entity resolution |

## Quality Gates

Applied across all repos:
- Unit test coverage ≥80% for new code
- Integration tests for every MCP server tool
- Ruff + pyright clean on all Python files
- ADR compliance verified for schema changes

## Dependencies

- **Reads from**: All repos (test results, coverage reports)
- **No repo depends on this** — evaluation is observational

## Conventions

- Python >=3.11, uv, hatchling, ruff, pyright
- Pydantic v2 for all models
- pytest with marker-based test organization
