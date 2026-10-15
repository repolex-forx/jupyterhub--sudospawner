# Repolex Knowledge Graph of jupyterhub/sudospawner

RDF knowledge graph data for [jupyterhub/sudospawner](https://github.com/jupyterhub/sudospawner), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/sudospawner
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 304be890e24a0d64c394ea26690a82bedb367681
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 304be890e24a0d64c394ea26690a82bedb367681
│           └── chunk-001.nq.gz
├── blob
│   ├── 08ee63cf94d541774db1d762e5a58a60a50baa21.nq.gz
│   ├── 0dc89813dc10ed07777226c26d348a19ce3afb93.nq.gz
│   ├── 15e5db461c24213595e12fce267b22659160341e.nq.gz
│   ├── 29cfc7bef93f08bdb21337ebc9f61773759bef70.nq.gz
│   ├── 3dbff1c4f891e7f688d3a267590727f08b2bdd67.nq.gz
│   ├── 4612e1d99e1506ef2bac3e649ac440fe294e84ce.nq.gz
│   ├── 49d7ed16f5986ff0a97f5b5cfe45510187e42788.nq.gz
│   ├── 4a90ef35f66750bef24c2de3198ed2fa276c4b5c.nq.gz
│   ├── 4aba2322b1b7f3f805c961b3a6550fc33b6dfe59.nq.gz
│   ├── 54f34614ae7c04a58091d341358a92c68e8da14b.nq.gz
│   ├── 69521b1221670a5ae10eac77ff018f386c78f863.nq.gz
│   ├── 698ad83bf585ee8b8df0e7eeb52b70bc53555d73.nq.gz
│   ├── 815a9af14e2dd40f998a82afe49089c84b973810.nq.gz
│   ├── 8d34bf0659e125f777c98cf96b58f11b755c5bef.nq.gz
│   ├── 9da152bbfd8a4bc2db9e6ce31da087aba5c103bd.nq.gz
│   ├── ab119b2586272c29793685c7958b718b7a43d335.nq.gz
│   ├── b2d52abe7b0ca0c0933c77357d1df4cecde71320.nq.gz
│   ├── b9e78fd55447085415609e431e91ef7664166a75.nq.gz
│   ├── c49c19c96b661c846e73e158eea379eba0b14203.nq.gz
│   ├── c903acd554739db9ac5c2b54f790e37a38cdf421.nq.gz
│   ├── d5855938088022e3440c09d8a79a4206e12de2c4.nq.gz
│   ├── d778f9f931e1da8aaa2f6d2d9198fd85019b0814.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e86b052721615a4955cea717e4c8278b811ce543.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 304be890e24a0d64c394ea26690a82bedb367681.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[jupyterhub/sudospawner](https://github.com/jupyterhub/sudospawner)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
