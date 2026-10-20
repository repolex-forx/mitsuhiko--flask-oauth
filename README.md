# Repolex Knowledge Graph of mitsuhiko/flask-oauth

RDF knowledge graph data for [mitsuhiko/flask-oauth](https://github.com/mitsuhiko/flask-oauth), parsed by [repolex](https://repolex.ai).

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
rlex download mitsuhiko/flask-oauth
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── af6432621a9add5e55b0d7638e1380f66f3d4ed0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── af6432621a9add5e55b0d7638e1380f66f3d4ed0
│           └── chunk-001.nq.gz
├── blob
│   ├── 00221f3a1cee77377f261ac9428d2469c54848cb.nq.gz
│   ├── 1c9140cac664ea8921c40e4404cc9b95c97bcd61.nq.gz
│   ├── 1cddd10c27f6c6379fda78e70b293f0834b67d52.nq.gz
│   ├── 2c0e9301088fd5c251989377c631a823557c6b29.nq.gz
│   ├── 34d940dc8bf23ec32e984cf89dd27a2b4646c899.nq.gz
│   ├── 3dca9226bc979caa9252a2cc46fffc898a797c90.nq.gz
│   ├── 536516d639fd9a96202eeae0540352ed1e12bb7d.nq.gz
│   ├── 536836a7a7523956864c63a3394f52cb67eb04bf.nq.gz
│   ├── 562f7eb602f1966cfa4276aaf8d5956959091acc.nq.gz
│   ├── 680e7a5a8005e0d2b9c6184b6d5e412ff053bbab.nq.gz
│   ├── 746b6b9f80c71049f2a4eb84ff72d5d1bf77c62c.nq.gz
│   ├── 9b99664b655a51e888b28955b5ef9fd3b6dbb6aa.nq.gz
│   ├── 9d8335a2df6406030e3edc638c5f18ffdc35a8ea.nq.gz
│   ├── bf7b494fc7044e1395c1c821f2babc309277bf78.nq.gz
│   ├── c7ba0fc9414473b558683e2d9545cfe79402fa03.nq.gz
│   ├── ce7954ab12080e1cfb0583669a58267bea008a44.nq.gz
│   ├── da3116d180cf954bc8a863f3bc26d6d97ca33937.nq.gz
│   └── e1da1e271584152ec2240f027023c9c256ab34fa.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── af6432621a9add5e55b0d7638e1380f66f3d4ed0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 26 files
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

[mitsuhiko/flask-oauth](https://github.com/mitsuhiko/flask-oauth)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
