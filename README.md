# Repolex Knowledge Graph of scipy/scipy_doctest

RDF knowledge graph data for [scipy/scipy_doctest](https://github.com/scipy/scipy_doctest), parsed by [repolex](https://repolex.ai).

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
rlex download scipy/scipy_doctest
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1bcadb1d88737182c80a75a402d01de129928ea5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1bcadb1d88737182c80a75a402d01de129928ea5
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ce2187db7ec5f46dfbcc9dccde992ef59c20950.nq.gz
│   ├── 165d5d4386b32d54beb856d6904e58d87a1101fa.nq.gz
│   ├── 1d65b0e6ffff3aef3d2563dd277fb5f1d0419e12.nq.gz
│   ├── 23953f2ae17bedd5f4a989dfe7851deca9929bf0.nq.gz
│   ├── 262540a7f22fb125c98f078ffb5403e4825de437.nq.gz
│   ├── 277d8c03cb2e1e37ca9826fcd1e985722aa4515a.nq.gz
│   ├── 2a9929ca1808a16bbb59c970c358c545a30ff7a5.nq.gz
│   ├── 2ae14c70984f135bcbbc7f8c37b33889816391dc.nq.gz
│   ├── 2efc8e5726e9a23ee54586d5aa0a645e89ceab4f.nq.gz
│   ├── 30f03d6b77368a2764f47f6d1dccb00f3f4522b1.nq.gz
│   ├── 32e129b160cd374c89f22830e99cbc0d65e52b7e.nq.gz
│   ├── 366b8c9b925bb585762d585421f8d05d9a411186.nq.gz
│   ├── 3988ff61f61c43bcbc2b45a613b647de8bb81993.nq.gz
│   ├── 439d906abbc992b8a6bb05c945516d24fc58ee75.nq.gz
│   ├── 51069a45e06b917540de16199bf6e4b015971d4f.nq.gz
│   ├── 51bf790c33d3a54b140ea43e5034f7ae7186398d.nq.gz
│   ├── 5a4ac873d1cefcc0e66e6a67134f0658d91f2b82.nq.gz
│   ├── 5aa84e3ecc0171ea4fc45849278e25acf6e681c1.nq.gz
│   ├── 617cd9dbb5fdb960c59932ef81b0f8403cf7f255.nq.gz
│   ├── 61e3702bb93852ec913a8b88f3f1dbd1d5e616e5.nq.gz
│   ├── 6c81c636649ad0102b51ad7875a3f4f8ccd872b1.nq.gz
│   ├── 85a35c8f7df916f356dcdc5b240359cc817a798c.nq.gz
│   ├── 868dd0f2e1699df539b0457fa929a16cda306880.nq.gz
│   ├── ad3fb33061d2c18552ca8e0f0cd4c1ae813b2a0c.nq.gz
│   ├── afa0f1dbd05f129211113b5b003340dadabd243f.nq.gz
│   ├── b0392b967cbb25d54a088096ebc0203e7a283475.nq.gz
│   ├── c960409cf46d4da7ba85492b234dc443498a2be5.nq.gz
│   ├── cdaecfef052fbd857ff427cefc539d537067fb33.nq.gz
│   ├── d5e6609efe2fe00eb5e0e685cf8600e8249d558f.nq.gz
│   ├── dd5d10f9e6810df21343622eaabcf5a555385d35.nq.gz
│   ├── dea8aec5a49bbf09671fb5fc00248554bd33d48a.nq.gz
│   ├── e049e3d62d410d481168d5c15e6e1ee2af893d23.nq.gz
│   ├── e257a6f48575503673891e501649dc061fc3b954.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea91d5a790d0a825cd7bcc61d846d8ae8f1fbd32.nq.gz
│   ├── ead7f06870c519df1f26abe41a319a4c8842ab3d.nq.gz
│   └── eb852ba1c45b2d8b3f9a7ecd9318aeccefce87ec.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1bcadb1d88737182c80a75a402d01de129928ea5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[scipy/scipy_doctest](https://github.com/scipy/scipy_doctest)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
