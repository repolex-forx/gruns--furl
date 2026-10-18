# Repolex Knowledge Graph of gruns/furl

RDF knowledge graph data for [gruns/furl](https://github.com/gruns/furl), parsed by [repolex](https://repolex.ai).

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
rlex download gruns/furl
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 46d9ea79c98bb14b970a199fb924705d024f29ad
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 46d9ea79c98bb14b970a199fb924705d024f29ad
│           └── chunk-001.nq.gz
├── blob
│   ├── 266881f4b8123eeb882823bc3491f6e0fbc06cbf.nq.gz
│   ├── 355959e39cc8df773f2e57ab83d2e6fe43153d07.nq.gz
│   ├── 3949106656ba0729ac229d2d53ab5081c71ab0c2.nq.gz
│   ├── 446e8e4eadbba683c4f63a85b734f7fbfa700838.nq.gz
│   ├── 548d6c0986d34fc614e257b5b75cfd028916e063.nq.gz
│   ├── 5a8edc0e1d30e6809371e3085305218064fec71f.nq.gz
│   ├── 5ace4600a1f26e6892982f3e2f069ebfab108d87.nq.gz
│   ├── 63d6204f46833ecc5a1bac446a14ee24f7ab5d3c.nq.gz
│   ├── 748c38058c44b443b09df6421df562207de75a1a.nq.gz
│   ├── 74bb6c689fb0859fdddae9da13fe84504d11bb7a.nq.gz
│   ├── 811d1606a02aa74aac0743a75e497ee41b58139d.nq.gz
│   ├── a001657ad516727f9a92e2667949fb6ee1e21916.nq.gz
│   ├── a7bdf864f91818474e2d36e43cab1e0bda099689.nq.gz
│   ├── aa58c9f78082d6f2b75444b82881a0361577cdff.nq.gz
│   ├── b15543a6e80f1c2e7ba4d2d88b4bee9f47a27e44.nq.gz
│   ├── b6289776d8d70dabbfe0e04a9ca7c22cc30a2132.nq.gz
│   ├── bc268c8227ff462dcd1dc1277c5235ae67049d7d.nq.gz
│   ├── c1b5780facf5098628e40d39fcec310954c10b3a.nq.gz
│   ├── cd6d71070e7c7319f0687a7acc2ef056845f1f92.nq.gz
│   ├── d433b8e1fc06f4c50b8b6a3aefaae7315a522c93.nq.gz
│   ├── d70e86db3133ad570cd0e68400974073696ed061.nq.gz
│   ├── ed374f5849d40062186e12542984ec80c98cc82e.nq.gz
│   └── f6a17d77b32f6fdb07f997d0d1220320a6e6de36.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 46d9ea79c98bb14b970a199fb924705d024f29ad.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[gruns/furl](https://github.com/gruns/furl)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
