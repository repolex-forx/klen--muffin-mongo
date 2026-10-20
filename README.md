# Repolex Knowledge Graph of klen/muffin-mongo

RDF knowledge graph data for [klen/muffin-mongo](https://github.com/klen/muffin-mongo), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-mongo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fdfa40b2b6aa4eed418a76a6d45972b84a56ae10
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fdfa40b2b6aa4eed418a76a6d45972b84a56ae10
│           └── chunk-001.nq.gz
├── blob
│   ├── 01ee85c43789fcf28896f0d1b9386fd41ce23ef4.nq.gz
│   ├── 09942a544befbeb622d681c7943f3a3fcd77ba6f.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 0b2e907c89333ea1b1c45cf476f5afdd63c69c08.nq.gz
│   ├── 1386365f094a748ec5d08a7c28f0f9c4e939ed08.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 26b63e17d8ebc8389300f2245515cb0db4c494b9.nq.gz
│   ├── 2a826403bc5602311bee00f7a5af6be7baeab1a4.nq.gz
│   ├── 2af47f4e4c1b4fe37fa31c44a8a540f629ecd8b0.nq.gz
│   ├── 5c295c4b9811b9bdf3ea6c7e80f5e0e03a7d14c4.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 6181098b545928389ee23835bf7e8e450684d8b8.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 8145ae04108ece8567bb7fbfe88a1382b6179fff.nq.gz
│   ├── c925c22d90a0dc57ce7b56fa64c9036c58f8f898.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
│   ├── e758a4165b38ab0b03df9738d7bb792ffc289e9c.nq.gz
│   ├── ef23051ba28a3e87238a94de1f097f9bbd894ac8.nq.gz
│   └── fc9b006dd704aae77aebcfe9e6d7c6d6f6692eec.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fdfa40b2b6aa4eed418a76a6d45972b84a56ae10.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 30 files
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

[klen/muffin-mongo](https://github.com/klen/muffin-mongo)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
