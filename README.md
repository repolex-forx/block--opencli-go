# Repolex Knowledge Graph of block/opencli-go

RDF knowledge graph data for [block/opencli-go](https://github.com/block/opencli-go), parsed by [repolex](https://repolex.ai).

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
rlex download block/opencli-go
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 55adcb6353a09e1f45355b12f86466d2ae88cc38
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 55adcb6353a09e1f45355b12f86466d2ae88cc38.nq.gz
│   └── repolex
│       └── 55adcb6353a09e1f45355b12f86466d2ae88cc38
│           └── chunk-001.nq.gz
├── blob
│   ├── 014a291e96c95f1c15d037a01e7b3f903ab76a98.nq.gz
│   ├── 0367d2331a2cbfb3dadb43da08affe106a235c28.nq.gz
│   ├── 081cbe83449cf8e625a3e2e79b6b35415c4e1503.nq.gz
│   ├── 0ba9db25329d0b336e39ca8cde8470c5b7bc45eb.nq.gz
│   ├── 20a9e76fbcc7a888d461b5f5302133c32f950f15.nq.gz
│   ├── 25f0bc5ed80683a81f46e6bfd1cf8ea0b56c6807.nq.gz
│   ├── 383f4511d444516caed0fd113ee8a2b640cd2290.nq.gz
│   ├── 46a075c7bf4218e0bd9278426f5284bcf0abe6e9.nq.gz
│   ├── 46da95df7291c1f80c2c537997097ca4da4c7389.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   ├── 862ee3c28647e7a58801a75236855c269c1448ae.nq.gz
│   ├── 87acaadba3d3a97cd17d084637a6cdd94caf2167.nq.gz
│   ├── 8a128c522cb64713c06295a7352892d038fbabeb.nq.gz
│   ├── 9582fc588754f78d9875691a3bd5e674295436b3.nq.gz
│   ├── 981d030a0c890ff64d8e81ba4cab39757900f064.nq.gz
│   ├── aa8e0db2b39dd45e9a37447e7fe2364a331d3511.nq.gz
│   ├── c64fa520d864b7d48fb2444292c3469db0c6d482.nq.gz
│   ├── e889550ba4cbc92a720527042e5f6e7a303bfcbc.nq.gz
│   ├── eddf6967cf7e20669f11f2a16ecffa7176d7edb6.nq.gz
│   ├── ef87a2566ba8589adfb837fcf0a1139602f918ee.nq.gz
│   └── fe28214d3352b0ed40820a4999317694c8b1ef57.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 55adcb6353a09e1f45355b12f86466d2ae88cc38.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 30 files
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

[block/opencli-go](https://github.com/block/opencli-go)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
