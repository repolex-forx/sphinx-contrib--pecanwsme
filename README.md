# Repolex Knowledge Graph of sphinx-contrib/pecanwsme

RDF knowledge graph data for [sphinx-contrib/pecanwsme](https://github.com/sphinx-contrib/pecanwsme), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download sphinx-contrib/pecanwsme
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e2478155475b7b3130ae62ed819570cde7f6a444
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e2478155475b7b3130ae62ed819570cde7f6a444
│           └── chunk-001.nq.gz
├── blob
│   ├── 26dcd917af49970abc1da26cdf0c2e0f5d8fff0e.nq.gz
│   ├── 37113dd2a513a24a0eafaf8e1755df4e4b1bc670.nq.gz
│   ├── 4143aac26d5e88f5faf53c889c069b2aefa9b4ab.nq.gz
│   ├── 487ccb3ec9066f0ab5eda91a695018d2a33ec3a9.nq.gz
│   ├── 4df3b687d0f9340147381d9f558016156a7bd034.nq.gz
│   ├── 657068a893003b51d53a3cdadb2a662527b944b1.nq.gz
│   ├── 68c04af45d5839181e7d95fb22397cfafb29956d.nq.gz
│   ├── 7f9460861695ef8b52a961f028e098f5ff45b829.nq.gz
│   ├── e37435e3c532546c1ffaef8d985d4ba7c17536ff.nq.gz
│   ├── e67cdfae857dad11e0167655a73cdb5650b95af1.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e2478155475b7b3130ae62ed819570cde7f6a444.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[sphinx-contrib/pecanwsme](https://github.com/sphinx-contrib/pecanwsme)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
