# Repolex Knowledge Graph of NousResearch/hermes-example-plugins

RDF knowledge graph data for [NousResearch/hermes-example-plugins](https://github.com/NousResearch/hermes-example-plugins), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-example-plugins
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 38fe0fb53eff98d477f807432e965429e665ca33
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 38fe0fb53eff98d477f807432e965429e665ca33.nq.gz
│   └── repolex
│       └── 38fe0fb53eff98d477f807432e965429e665ca33
│           └── chunk-001.nq.gz
├── blob
│   ├── 04092348ffbf16da90db79e081ecc167b9d435e7.nq.gz
│   ├── 0b2ba4bdf657c9e220cd624c565ceccd85f60a21.nq.gz
│   ├── 111b87dfbd5ef6db00f24bf9b2f0ba4064180072.nq.gz
│   ├── 20aed76e26feefc5cf05cda23170afbb359b6645.nq.gz
│   ├── 2d22f050204893fa5ffeb9387fc86f1827715685.nq.gz
│   ├── 36f123ca7fcf06968b77228ab3852566d587f1e2.nq.gz
│   ├── 5700b997827973cb0eb6d84a2782bb08a5872434.nq.gz
│   ├── 652b70c9a0ecb5fa837347d9917aec4d7ce1e90a.nq.gz
│   ├── 6f56c586d268ac0d2fc6855a54ddc43fe833a847.nq.gz
│   ├── 7506c80997e9c77f60d65662e1f96ce791fa2f4c.nq.gz
│   ├── 7786dd0cbb835a6570dd8c758004e2d0a416266d.nq.gz
│   ├── 95fce2f100f4e7333dacd226cb1cb6bcc2cdc42e.nq.gz
│   ├── ccf0c29538fb8019d92eff333ffb69a2d9882b35.nq.gz
│   ├── d001181cd598a95761c3cdc40b7fff7770f562ec.nq.gz
│   ├── e6e5a549e19ff245b650ddfcc29a354c7a62541f.nq.gz
│   ├── ebbcf11841bd597536982dbd52025e46bf9aabf6.nq.gz
│   └── fec3c79eff925bee1ff75c14d694a1962f24a895.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 38fe0fb53eff98d477f807432e965429e665ca33.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 26 files
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

[NousResearch/hermes-example-plugins](https://github.com/NousResearch/hermes-example-plugins)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
