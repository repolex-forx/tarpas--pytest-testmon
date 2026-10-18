# Repolex Knowledge Graph of tarpas/pytest-testmon

RDF knowledge graph data for [tarpas/pytest-testmon](https://github.com/tarpas/pytest-testmon), parsed by [repolex](https://repolex.ai).

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
rlex download tarpas/pytest-testmon
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── dccc58d2ed8edec98096ff1974acb7c07d3e3482
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── dccc58d2ed8edec98096ff1974acb7c07d3e3482
│           └── chunk-001.nq.gz
├── blob
│   ├── 02bad24caec6c08178b0bfdb2f49612e0ad0f5d2.nq.gz
│   ├── 28fa9976c3b863e9af4006a9995dfddb78c7f31c.nq.gz
│   ├── 41f544f9ab83c97cfec6ecbd10772c0389dc2117.nq.gz
│   ├── 434f2c996b46171906e48ca7ecf7fa9d52a1a617.nq.gz
│   ├── 60b5521c4b1285c5c83faa5ea427e5ca5ee34081.nq.gz
│   ├── 6238fcb1b6b327f58d1f039e6617a68384ce5720.nq.gz
│   ├── 7d8b7e660dd9b32ad920e66bbd91b5403f41f08a.nq.gz
│   ├── 7f1a1763ca9cebc7bc16576d353d3284ee5d3c7d.nq.gz
│   ├── 8809e999fa594f917a13ee0d1a82fb22180d2202.nq.gz
│   ├── 88417912c1d19a93692732815af22e280845efa3.nq.gz
│   ├── 8ccf22293ebc5ca7aa8eae97abc73f88ae4b25aa.nq.gz
│   ├── 9b69c9330e0e68b9878a993664babbdf6373a0a9.nq.gz
│   ├── 9eb281611e3e4fb27ff69ee4463dafe24d31b71f.nq.gz
│   ├── a3566077428904fb249e2d52e59f65235d5b8a4f.nq.gz
│   ├── b580a4d0c216dc44d7437111c4ac0298a5232e44.nq.gz
│   ├── bbcbbe7d61558adde3cbfd0c7a63a67c27ed6d30.nq.gz
│   └── fff2c36b1bd9530bee3d8df56a68a5e50fdea34b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── dccc58d2ed8edec98096ff1974acb7c07d3e3482.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[tarpas/pytest-testmon](https://github.com/tarpas/pytest-testmon)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
