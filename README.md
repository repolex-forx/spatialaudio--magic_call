# Repolex Knowledge Graph of spatialaudio/magic_call

RDF knowledge graph data for [spatialaudio/magic_call](https://github.com/spatialaudio/magic_call), parsed by [repolex](https://repolex.ai).

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
rlex download spatialaudio/magic_call
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bcbf1f3997d5c66123a14a6cb17667d8f172507c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bcbf1f3997d5c66123a14a6cb17667d8f172507c
│           └── chunk-001.nq.gz
├── blob
│   ├── 3c6e79cf31da1c0433d2fa666bf50b53f6359f26.nq.gz
│   ├── 8ca1f543560cd402cb9922274d8102dccf97412a.nq.gz
│   ├── 9dbe03d27359a12d0280f9c5ff1a44ed0c7e097b.nq.gz
│   ├── a8d15b8c5571d8d66eda1841a806818c16b3b3d1.nq.gz
│   ├── c723b64fad47afce79165a6ca9cd5ceb64c39b9a.nq.gz
│   ├── ca88124ecb5e808685d2b5eaddbd915f2354f5e5.nq.gz
│   └── e91fd081501366035b9a4b856ef0d215a106cf69.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bcbf1f3997d5c66123a14a6cb17667d8f172507c.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 13 files
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

[spatialaudio/magic_call](https://github.com/spatialaudio/magic_call)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
