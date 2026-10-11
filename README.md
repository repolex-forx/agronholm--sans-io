# Repolex Knowledge Graph of agronholm/sans-io

RDF knowledge graph data for [agronholm/sans-io](https://github.com/agronholm/sans-io), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/sans-io
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4e0c9d23714f8e97288f0556d2eac9767a704bec
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4e0c9d23714f8e97288f0556d2eac9767a704bec
│           └── chunk-001.nq.gz
├── blob
│   ├── 10b73a64c698eedc3a04256c8096bef019ecb972.nq.gz
│   ├── 482384281f54acfa8f8331c241959c030c7f64fe.nq.gz
│   ├── 4adc76c76101ee3d57429161a1a073a5c0d80173.nq.gz
│   ├── 6898c141058fdb41964f1fe2412bf0c7ed02a9da.nq.gz
│   ├── 89234170d6becf549d7f01ed7dcfe6f0fbb8eed0.nq.gz
│   ├── ae11d04eee02023dd5ea0ea02155d39edd9e71c1.nq.gz
│   ├── b413d8c2524aab1c4ddbbb0f2761a1094261d111.nq.gz
│   └── f5c02a2c6840cfdb0c18790f104b2272defa0c54.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4e0c9d23714f8e97288f0556d2eac9767a704bec.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 14 files
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

[agronholm/sans-io](https://github.com/agronholm/sans-io)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
