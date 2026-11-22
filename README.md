# Repolex Knowledge Graph of dtolnay/path-to-error

RDF knowledge graph data for [dtolnay/path-to-error](https://github.com/dtolnay/path-to-error), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/path-to-error
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 097ed8772815ab6a676ebf3998b6de4770af090d
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 097ed8772815ab6a676ebf3998b6de4770af090d.nq.gz
│   └── repolex
│       └── 097ed8772815ab6a676ebf3998b6de4770af090d
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 20574e2d504af8d597955e380237d382a990f8c4.nq.gz
│   ├── 2c2871b7daa7ead69064ec7392eca4167dcbd05f.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 624967d6c6b7c04e5d31a59e5a6deca5af5e8b0f.nq.gz
│   ├── 6870792143ab353e8d70c4cdc2eecba43e74e17c.nq.gz
│   ├── 6efed45074cf43a5500693360fc8cfb44aab44ac.nq.gz
│   ├── 722066dd5b75a485fa72efa74cbf3e9a60cfb6cb.nq.gz
│   ├── 750707701cdae985156601cc906195021ba6a6e5.nq.gz
│   ├── 883aef5f0cfa08144cabd383c045f4eaac5b2922.nq.gz
│   ├── c90ba4da0af6ecf91343192e738d0fe0e3ca2dc9.nq.gz
│   ├── d730995a716881805a861636d411b36f5cdb5842.nq.gz
│   ├── e9e21997b1aca0707f8749ea13c09aec66c899d2.nq.gz
│   └── f0abba327505536ca9cc373a9b92ec0d2b6bd327.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 097ed8772815ab6a676ebf3998b6de4770af090d.nq.gz
├── filetree
│   └── 097ed8772815ab6a676ebf3998b6de4770af090d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 24 files
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

[dtolnay/path-to-error](https://github.com/dtolnay/path-to-error)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
