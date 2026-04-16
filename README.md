# Repolex Knowledge Graph of anthropics/healthcare

RDF knowledge graph data for [anthropics/healthcare](https://github.com/anthropics/healthcare), parsed by [repolex](https://repolex.ai).

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
lexq download anthropics/healthcare
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f77843986830f65e040507240bb33f22a7fea06c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── f77843986830f65e040507240bb33f22a7fea06c.nq.gz
│   └── repolex
│       └── f77843986830f65e040507240bb33f22a7fea06c
│           └── chunk-001.nq.gz
├── blob
│   ├── 1c8aadf144d74fe6044287f3f6a333cfb7575db9.nq.gz
│   ├── 1e28c31bcc279518652379fc4de4bd7aec75f27e.nq.gz
│   ├── 21623c5035d50511d7f4f3f13b9c54fce7433da0.nq.gz
│   ├── 2bc2acd2f1d7dbe5ae4f0b340012de704804d978.nq.gz
│   ├── 302c999ad9f1a5cb942a6765d6c5c1c173214436.nq.gz
│   ├── 36ef00d5e9fa74961679be47bcae8e25ba1c9bca.nq.gz
│   ├── 38af9f5ff72d2650371b476dd37963b4a1f25801.nq.gz
│   ├── 40c3be0419e1b145d4dfdf6c3cb3447336f9e2a5.nq.gz
│   ├── 5c6923a859e682a7e56183ba739d94ed03c69c08.nq.gz
│   ├── 647c8f15860b2d2c8cc76669c4bd0a49399991a7.nq.gz
│   ├── 6d5acff80f431a6b8ed287b70a2065adc04af0e9.nq.gz
│   ├── 7302992037511d5ae9d21afa07db173573555fa4.nq.gz
│   ├── 7b55611e89dfa7ace30b52e8e6c8c52110beac64.nq.gz
│   ├── 87e3fc743ae469040903c93512d3347fc4628fbd.nq.gz
│   ├── 8864aab9b26654c83ac87223c2ddba69e4467d67.nq.gz
│   ├── 9052fe801cee3a59a2e75fb06a6997a1ed2c65b9.nq.gz
│   ├── 9483e8edd9fad6a743c5c15fbd57a8b9d08e3709.nq.gz
│   ├── 95e009ddecb268f5710d90186951dc98b46d56eb.nq.gz
│   ├── 98721ae266f6e3a7d928fae22b3e35dd17692958.nq.gz
│   ├── 99489b57ee500c4982e576872a3d4cee2dfa2038.nq.gz
│   ├── 9bada335b4ee0e3ec5b896f7cb0a70b2a87aadc9.nq.gz
│   ├── 9e1cc83215125f376f925ee267579474c5c44103.nq.gz
│   ├── b69358f1853c93efd4ad9520d32373e485e56199.nq.gz
│   ├── ba21f671fa3bfc262bf214dac20795d6e19b89b0.nq.gz
│   ├── c2b0812028c239a91a5d0418c0f04193927fe75a.nq.gz
│   ├── c9f2dce92159f433e85eb84b9f07ebf4553b247e.nq.gz
│   ├── ce4580b959d4e8736e36105c79a8ae13682133bd.nq.gz
│   ├── d0e9e6f9658c0f23d860fc7020750dad41564234.nq.gz
│   ├── d32014be9dd57745f8db3d4ccd28addad07d9d8b.nq.gz
│   ├── db6beacc410fc1b91c62f097ff78d13cf6e101e9.nq.gz
│   ├── de43bd37d4b5627b2a60255d67b4a395fe9da8c6.nq.gz
│   ├── f1ba1f126e20cd7d0d1b0522e91209d0053d7e13.nq.gz
│   ├── f41ca7f600a50e4c19faa15028539d966b5adcb6.nq.gz
│   ├── f477487cc1594f3a9308073e5ae705a51a83c341.nq.gz
│   ├── f608d34b4fbbb85bc77f4a9cece8f8bb1f0aa855.nq.gz
│   ├── fad3128286acfbe1a1ec296e3ee0b2e9c29362b3.nq.gz
│   └── fde5233c882a08da57c78d5ac354123b728ba435.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── f77843986830f65e040507240bb33f22a7fea06c.nq.gz
├── filetree
│   └── f77843986830f65e040507240bb33f22a7fea06c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 47 files
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

[anthropics/healthcare](https://github.com/anthropics/healthcare)

---
*Parsed on 2026-04-16 by [repolex](https://repolex.ai)*
