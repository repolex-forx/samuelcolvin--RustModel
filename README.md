# Repolex Knowledge Graph of samuelcolvin/RustModel

RDF knowledge graph data for [samuelcolvin/RustModel](https://github.com/samuelcolvin/RustModel), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/RustModel
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── df61fe03a31f415f6c643702f7ee1de6c4451c0d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── df61fe03a31f415f6c643702f7ee1de6c4451c0d
│           └── chunk-001.nq.gz
├── blob
│   ├── 096c7ba6d5b059d7d423d81b174894826263304c.nq.gz
│   ├── 2f54a29fa06033a1ee9372539f1510d41371d6bc.nq.gz
│   ├── 35f56b4e721956ee482b8d0bc6ee5c4458131908.nq.gz
│   ├── 4c8f08402e674017f0316b8979b80f13f21c3268.nq.gz
│   ├── 7006dc0a564725e02d1276f0ba2b46d6cbe31ff2.nq.gz
│   ├── 7dc5d7a1242b7597124f26304faa30cba4023e79.nq.gz
│   ├── 87e260cd22e1fbb812baf155f22e46c52ad77469.nq.gz
│   ├── cfbff67b95815972adee0eafe0560504e160b660.nq.gz
│   ├── d166606ef9e091bb8dee691b06ab86d1f50032e4.nq.gz
│   ├── dd6b555687f7aa782715b78d3599c5af1cd1b765.nq.gz
│   ├── e6f728b6eaf85f95dce340fb92246eb1290d9997.nq.gz
│   └── f378d1afc46def32c67cbbd8550cfe9e8d05451d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── df61fe03a31f415f6c643702f7ee1de6c4451c0d.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 18 files
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

[samuelcolvin/RustModel](https://github.com/samuelcolvin/RustModel)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
