# Repolex Knowledge Graph of python-trio/outcome

RDF knowledge graph data for [python-trio/outcome](https://github.com/python-trio/outcome), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download python-trio/outcome
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4037dd7fa89b3a26f41594607bc94aaea422d7c3
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4037dd7fa89b3a26f41594607bc94aaea422d7c3.nq.gz
│   └── repolex
│       └── 4037dd7fa89b3a26f41594607bc94aaea422d7c3
│           └── chunk-001.nq.gz
├── blob
│   ├── 003bd6784ac08eb8723331ef8d97a277ba513903.nq.gz
│   ├── 004b72dad21473d34509b5b53e8b97b5cc341721.nq.gz
│   ├── 18bdb45f3961ef7ff5517a1a2b3837cef73fb158.nq.gz
│   ├── 1c2d6c2f4d5ba10d66fef4227ae66e6ab4adadeb.nq.gz
│   ├── 1cd2f251fc56922835d651eddfe77a362376404d.nq.gz
│   ├── 2827ac8fad21e966eeafd63640fd4d63dba2257f.nq.gz
│   ├── 291bfeaa3b207e4173c50080f22cfb473363ee5a.nq.gz
│   ├── 2c55784d0c9a24081d2dc0f69f35448258eabd89.nq.gz
│   ├── 2c71c9d662a8386fb39cb4c7d1bd35c67ea1275e.nq.gz
│   ├── 35b284d44a0f9a488ab904ecc7533a315f468f01.nq.gz
│   ├── 518b8c375d090ddda558aa282ee2b8e4d6e334f1.nq.gz
│   ├── 51f3442917839f8e0f0cccb52b3c10968ad0779e.nq.gz
│   ├── 5ff95fd41debf44b3efe4980633797570f7fb62b.nq.gz
│   ├── 75d83eab6ac3f3529a66120b81050b285229ccd7.nq.gz
│   ├── 7a81f0ef5c31c6a6e3699f32cd078e3958f10ce9.nq.gz
│   ├── 7e0298f61f6c8e3d3653c4064980c6461dd63ce8.nq.gz
│   ├── 855d7761c12f0e5712ca119c1241bdac2db867bb.nq.gz
│   ├── 98ad50f98cefc94a6db7fb4be02867acb50b0b67.nq.gz
│   ├── 9e6b453710e3a42b0dbc02a5fc58ccbe22513ef7.nq.gz
│   ├── a51266edb77f398acf910ec3ff17366e95b837bf.nq.gz
│   ├── a852d57ef7a643cdf1b5fe5a9c230048decd222f.nq.gz
│   ├── ab6c0a683364206b848d63571829cf09a36c55f0.nq.gz
│   ├── b76dd38bb632478a6658ae6cf90c68e8c932dc51.nq.gz
│   ├── b8bb97185926d7daed314609753173945ed4ff1a.nq.gz
│   ├── c41a4e6dd9ee157d61b021027bc0528dfd47dbf5.nq.gz
│   ├── c48b06785d5c42eae19c7233a8cf907cd9378555.nq.gz
│   ├── d3a27dc41aaf81846f0867137e2a4ffe1bc1bf97.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── da6abdf2ce977fc22ed876f6b16a95a7fa4341da.nq.gz
│   ├── e01a82068df81f5e6f741ba2b09d08d2ac43662a.nq.gz
│   ├── e3f825cb6aa102e611c8e5fc7caef0b09c776024.nq.gz
│   ├── e5b239009f9f8e3b4916f21e9ffa0919b348e2db.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e8a9f09379921964c5178004e508f31a9de8875e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 4037dd7fa89b3a26f41594607bc94aaea422d7c3.nq.gz
├── filetree
│   └── 4037dd7fa89b3a26f41594607bc94aaea422d7c3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 44 files
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

## Source repository

[python-trio/outcome](https://github.com/python-trio/outcome)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
