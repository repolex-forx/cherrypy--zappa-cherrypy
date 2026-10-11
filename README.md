# Repolex Knowledge Graph of cherrypy/zappa-cherrypy

RDF knowledge graph data for [cherrypy/zappa-cherrypy](https://github.com/cherrypy/zappa-cherrypy), parsed by [repolex](https://repolex.ai).

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
rlex download cherrypy/zappa-cherrypy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ae2e6da5e719ae7a811066e99521b85635ec2876
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ae2e6da5e719ae7a811066e99521b85635ec2876
│           └── chunk-001.nq.gz
├── blob
│   ├── 5a18fe13ae3b75cd526bbea38dbc2ed383fc6d8b.nq.gz
│   └── bc6d4cd1ac87f3f8611a5092d8d9ee3e75c0e1ff.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ae2e6da5e719ae7a811066e99521b85635ec2876.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 8 files
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

[cherrypy/zappa-cherrypy](https://github.com/cherrypy/zappa-cherrypy)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
