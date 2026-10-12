# Repolex Knowledge Graph of simonw/datasette-block-robots

RDF knowledge graph data for [simonw/datasette-block-robots](https://github.com/simonw/datasette-block-robots), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-block-robots
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 84702338300cadcb892f578c7b4b74f411505708
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 84702338300cadcb892f578c7b4b74f411505708
│           └── chunk-001.nq.gz
├── blob
│   ├── 12f1a40b216b096809057d3cd7c445a4e36859db.nq.gz
│   ├── 45ec37cb1a45331e6a40260716475a31ada4283e.nq.gz
│   ├── 4aa1d308a9b6cd4ed9e0e1a0bf99879a181e25d9.nq.gz
│   ├── 625f3fca6d7e8efb074b8c7ca849b2981007034c.nq.gz
│   ├── 8718a96e19fb3275f616244bcfc6b13b2bd261c4.nq.gz
│   ├── d07256dab453e5590f34199dca2c55f533bc0d33.nq.gz
│   ├── e40129626db60dc6df288dcf6d5be6e03a8584d8.nq.gz
│   └── ee130bd1322911b99e686fa8e1c7e1a786373b9d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 84702338300cadcb892f578c7b4b74f411505708.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 15 files
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

[simonw/datasette-block-robots](https://github.com/simonw/datasette-block-robots)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
