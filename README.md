# Repolex Knowledge Graph of cookiecutter/whichcraft

RDF knowledge graph data for [cookiecutter/whichcraft](https://github.com/cookiecutter/whichcraft), parsed by [repolex](https://repolex.ai).

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
rlex download cookiecutter/whichcraft
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 226393eca8b181e44d2e1ce1baf7d79d5a3a661f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 226393eca8b181e44d2e1ce1baf7d79d5a3a661f
│           └── chunk-001.nq.gz
├── blob
│   ├── 00d8dc08e0853540f815918934265d67e4fe65ca.nq.gz
│   ├── 23a5697fb323931518ba80ef894dcf9073138c80.nq.gz
│   ├── 2685e070b08818d2d91fe596a7037e0698bd4b37.nq.gz
│   ├── 383bad96a14b0e639d65bde6353fcd7a7cc78dab.nq.gz
│   ├── 3a2c532881a13b271f132cd2b9c5f7956de68515.nq.gz
│   ├── 41c4bf958df49600988c3f1b243febaa2488fe3a.nq.gz
│   ├── 51a1a5f21ad518ac754a091db514cabe12b92459.nq.gz
│   ├── 58b63d2ef6e7b4311c8d202c61f749314e06e66c.nq.gz
│   ├── 6ed28727981b55d86be526f21094e2624dbdb8e7.nq.gz
│   ├── 816cd4edcd27fa47f0329fdc9fc88fe3d1a33c2a.nq.gz
│   ├── 82eabdf44dbd3b58e25a5600b2548cd8d5e907da.nq.gz
│   ├── a4324be0fb7a3ffec333644cbf7c31c9fda5ef14.nq.gz
│   ├── b2b864069f4b139da5274bdedc3a400dce35f350.nq.gz
│   ├── b5cab588ab45a63e83861b7198274af6fc15c6c3.nq.gz
│   ├── d8e4325dc54d6e1d89d458f6966d3b1d6c347410.nq.gz
│   ├── dcd6189ecd30b9fb102e7bca82764ca5caade568.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e7cf2d9b718c6e9d41f13ede55b4cb0f98bbcdd2.nq.gz
│   ├── f7cfe801b237da8c96e4d1a4b10abb30624a536f.nq.gz
│   ├── f93f0cb14b9c2a0ad777cd43c4475b86079a82be.nq.gz
│   └── f9bf1ca6676c4cc4cba281c1035e345936feaa91.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 226393eca8b181e44d2e1ce1baf7d79d5a3a661f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[cookiecutter/whichcraft](https://github.com/cookiecutter/whichcraft)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
