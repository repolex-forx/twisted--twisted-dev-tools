# Repolex Knowledge Graph of twisted/twisted-dev-tools

RDF knowledge graph data for [twisted/twisted-dev-tools](https://github.com/twisted/twisted-dev-tools), parsed by [repolex](https://repolex.ai).

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
rlex download twisted/twisted-dev-tools
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6a08511f7ecf873e497151358c0195b05c853973
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6a08511f7ecf873e497151358c0195b05c853973
│           └── chunk-001.nq.gz
├── blob
│   ├── 03aa993c4dce9a45d3788230a8695ccaba320537.nq.gz
│   ├── 143c0c1b27e943252509b9179f82e77023cf6490.nq.gz
│   ├── 15ce135148a21a90df90590e5a670830ae21e19b.nq.gz
│   ├── 1f04641f2f01e02a93ef1146422714bde87940ec.nq.gz
│   ├── 3e5295d85cff480043dac909b5f4be0f0d9bf2b7.nq.gz
│   ├── 400b71f949f68c435772c2388077547599bf20c2.nq.gz
│   ├── 4ba5d33e84849460a8fc2755fc03ff428860f688.nq.gz
│   ├── 566a8eab837001166880d9c7f8484b0454999789.nq.gz
│   ├── 9e53d5303396cbf502d2f01e9cef1a404f1f7546.nq.gz
│   ├── bf194a37d10576517123d1558c1ab3f7131b552c.nq.gz
│   ├── c135aea9a8410599d719833627a02a168ea25513.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea2cacf3a1b22e8686598a80ff149369c8115380.nq.gz
│   ├── ef16ce3f11044cd7aea44301617fda88e54516d9.nq.gz
│   └── f6ff3c3464ecc479e11652cdee82f1bdbd2f90ff.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6a08511f7ecf873e497151358c0195b05c853973.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[twisted/twisted-dev-tools](https://github.com/twisted/twisted-dev-tools)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
