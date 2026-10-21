# Repolex Knowledge Graph of pandas-dev/github-doc-previewer

RDF knowledge graph data for [pandas-dev/github-doc-previewer](https://github.com/pandas-dev/github-doc-previewer), parsed by [repolex](https://repolex.ai).

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
rlex download pandas-dev/github-doc-previewer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7a1ea7e96d1a24578ec35eedd4256a7d80c3fef8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7a1ea7e96d1a24578ec35eedd4256a7d80c3fef8
│           └── chunk-001.nq.gz
├── blob
│   ├── 198733d6d125282c1f3e032c32ea3d3048aeb4f6.nq.gz
│   ├── 2d1c34fd9d7fce19d2818d226c3ef6542d2ea9cd.nq.gz
│   ├── 4c618e9bc95846b7b4cace16d70fb31eca9f99f6.nq.gz
│   ├── 579a508dad3c9905ce2f574d872989d709058b23.nq.gz
│   ├── 61e1be6c5ea97fdc321e8360dfefc6c9a250a60e.nq.gz
│   ├── 64e10e667ef36373c818d5bb88fe1bc87ae97239.nq.gz
│   ├── 79d0202c00e8572564ec6da57da10a74f93069d8.nq.gz
│   ├── 7c1cd9c49b78b4d89df2c83ba7ea0a68f590704e.nq.gz
│   ├── 7d1f7da5e59fcace921efedbd5641f29d4d48cf7.nq.gz
│   ├── 9c7ea4ac3a0cbecbb6b05643b5c89acfe40db465.nq.gz
│   ├── c77de07284bd78377d120b3368e628d041643c7a.nq.gz
│   ├── e0ff89e97e4543977164c9678d428f76afe17d88.nq.gz
│   ├── e4d8a19f24389a71da1770684bbd0ede14de49c6.nq.gz
│   ├── ea8c4bf7f35f6f77f75d92ad8ce8349f6e81ddba.nq.gz
│   └── fb854a5827ba97bdb29f16407603de7c333d01ac.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7a1ea7e96d1a24578ec35eedd4256a7d80c3fef8.nq.gz
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

[pandas-dev/github-doc-previewer](https://github.com/pandas-dev/github-doc-previewer)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
