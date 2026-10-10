# Repolex Knowledge Graph of astral-sh/ecosystem-analyzer

RDF knowledge graph data for [astral-sh/ecosystem-analyzer](https://github.com/astral-sh/ecosystem-analyzer), parsed by [repolex](https://repolex.ai).

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
rlex download astral-sh/ecosystem-analyzer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5fa06d2043c3f7a95a808bc0df87ac9bb82c8e15
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5fa06d2043c3f7a95a808bc0df87ac9bb82c8e15
│           └── chunk-001.nq.gz
├── blob
│   ├── 014835144877ea9c926d027ece3e1a26290cf481.nq.gz
│   ├── 03ae00e1b55fd3297c272cb2aed780d6b62d9e85.nq.gz
│   ├── 042d237af8b8856f66819f980122f91a4a83797a.nq.gz
│   ├── 1918c62e67d8063f5c76f9b2906518d5ba33a3c0.nq.gz
│   ├── 1d5fe10480f4fce2cd9d027dec38d18a99e76b7d.nq.gz
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 3b4c884b1720aa491fce908e6e1a302110ac68b0.nq.gz
│   ├── 3ebd98a76bef515c231ada3574612d468fd09d75.nq.gz
│   ├── 43c994c2d3617f947bcb5adf1933e21dabe46bb5.nq.gz
│   ├── 43d26b56f6e8b199bed505224053740403cd3c5f.nq.gz
│   ├── 4a6b411a6e40903d9d1ef549f61588205894332d.nq.gz
│   ├── 51bc07864b5fe828acdd3044a301203816d41226.nq.gz
│   ├── 52df830e25f6bc1012dfb0d10a945801c74b1ff7.nq.gz
│   ├── 530a8e75624fa46f1957f5c579cd96e3a9228a80.nq.gz
│   ├── 53f6d31931ec195fd1806501cfc924e4e0aa7a57.nq.gz
│   ├── 575cd0f7319ead030d5cd41f3acfa643f181d1f0.nq.gz
│   ├── 680e0f169cd51a6d0ee26bb0431551303a93f8a5.nq.gz
│   ├── 6cd760fcacf2cf05eeb8af45c38c5192183e99db.nq.gz
│   ├── 77c8ce46b8ddaad3370059593e9663425d5dd01f.nq.gz
│   ├── 7b4d4c0d1a6c88d40acbc8480b448f397797cf08.nq.gz
│   ├── 7b62ce5aeda90e82187a030a547b62d86c36d42a.nq.gz
│   ├── ae75729f6a53751b5b316cc4444c2d94420ff256.nq.gz
│   ├── b3f084f5934f29f64b258dc705985da9cc0a6144.nq.gz
│   ├── b8110091f4615d0d8d2a53f5d5cd596730451538.nq.gz
│   ├── be700e8e528c60bdcc62b7ce2ef91999b4489a74.nq.gz
│   ├── ce6fefc809632ab5085e3a8c9637eeb5751bc28e.nq.gz
│   ├── cf1bb9271a84dc27957d2e63dccbcadbdf3da508.nq.gz
│   ├── d2323912a184809ff1238b05a813387378765986.nq.gz
│   ├── dcc686f091c64c19223b062993019f016de493e1.nq.gz
│   ├── e308e3a76cbbcddf063766df1b3d60a4e29be886.nq.gz
│   ├── e9ff329dc462339ac65101aafc68b8263b27bf1f.nq.gz
│   ├── f0feeedb91269f865b56676c7aeea36bcc48cd45.nq.gz
│   ├── f8c6067633efa2d8c53d99bb3a7f94b879b1d193.nq.gz
│   └── f8cc02dbff9111fb415e5d8d6c1af5bb91871bd9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5fa06d2043c3f7a95a808bc0df87ac9bb82c8e15.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
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

[astral-sh/ecosystem-analyzer](https://github.com/astral-sh/ecosystem-analyzer)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
