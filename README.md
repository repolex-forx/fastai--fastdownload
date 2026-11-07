# Repolex Knowledge Graph of fastai/fastdownload

RDF knowledge graph data for [fastai/fastdownload](https://github.com/fastai/fastdownload), parsed by [repolex](https://repolex.ai).

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
rlex download fastai/fastdownload
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2c90ed8ef4ffdb98678b4abcccd46128435ab1c7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2c90ed8ef4ffdb98678b4abcccd46128435ab1c7
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d026da9d17ee53361d2d61a829532a61bdc9f3d.nq.gz
│   ├── 12b31d5b2b4eb82289ffcf259bc75698c1e2db76.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2c0831b40d481fe2e77cd9246f6e5e004cf64cbe.nq.gz
│   ├── 33185910ea16b360fd1c6e130f3d2513362ff09a.nq.gz
│   ├── 38fbde548847377b547aeb7e695dedc2e928f5a2.nq.gz
│   ├── 396763121083b97dc7343b3ee3d61efb23ddee41.nq.gz
│   ├── 4e038bfdbcded62c2a248b9432d7454e23853e83.nq.gz
│   ├── 4e167bebbbe400dd79d5a22b44b311bb7f962dc2.nq.gz
│   ├── 4f7288dcae3075e2c958b7ae29cb8f2875c5ade9.nq.gz
│   ├── 55a7ff0ead4ddb4bb58827c36e649a5360050e47.nq.gz
│   ├── 5843914a696b1ea582f2af8336ec14413d1146ac.nq.gz
│   ├── 59a1e49ccb865267d2876aceaa46902ddda51d62.nq.gz
│   ├── 98a60bd3bea750b3a938bddc2e10d34bc297f8c5.nq.gz
│   ├── ad416e33057313679180dd1640995be83f060061.nq.gz
│   ├── b6144806b823fc0ff70d54508a32371d5826049e.nq.gz
│   ├── bf32e94a454bf4810837d19083594260118f9767.nq.gz
│   ├── cbad3ee271d5a888f6b632a4ef8411e7ce58ec63.nq.gz
│   └── dbcb8980b8ebe91ff761e34acae32304808a32b1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2c90ed8ef4ffdb98678b4abcccd46128435ab1c7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[fastai/fastdownload](https://github.com/fastai/fastdownload)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
