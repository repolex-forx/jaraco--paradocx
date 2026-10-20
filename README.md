# Repolex Knowledge Graph of jaraco/paradocx

RDF knowledge graph data for [jaraco/paradocx](https://github.com/jaraco/paradocx), parsed by [repolex](https://repolex.ai).

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
rlex download jaraco/paradocx
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 68b1e2b1a77087b4058130e90e16169201ff4387
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 68b1e2b1a77087b4058130e90e16169201ff4387
│           └── chunk-001.nq.gz
├── blob
│   ├── 10d412f406891b9683f832fcbc134c9bdf4f916e.nq.gz
│   ├── 19344060307f72c0c75b69a9cf48ff0bdc4faec8.nq.gz
│   ├── 1f2aa7533b0423a8eb943f6f4ec02498e39581a0.nq.gz
│   ├── 278c4b0c3e91bdb7122363c817dadce471b02a7a.nq.gz
│   ├── 2d2c489af30999f8985f355fb2c252fba0b3ee85.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 2efb1a914f320ddb10d86c5e5fdc7cc3c6466ca3.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 46cc54051f1cac71f0b786647bbd83277f4bb5e8.nq.gz
│   ├── 54c9000ec94341dd65c2053251b85b124017b9b5.nq.gz
│   ├── 54cc8303b22089e12053e552d4e6cb852a865b8a.nq.gz
│   ├── 577e87a793a20e413f7321f4f17ec1eba2ea1962.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 61aab60520a5d37d96020e097bedeaf9ae3b48a7.nq.gz
│   ├── 650b837e57eef1c1a219714ae0e97c660a2f3ab1.nq.gz
│   ├── 700235be57c1b2872455c0be5333f59cf568e252.nq.gz
│   ├── 71015b2097c4aa4dc8b653f1d22221056d91c006.nq.gz
│   ├── 72316a53c085c3d552243da3702c49a7ac29be2f.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 7c75b2b2ca7ee567e6813f4642ec855e59a049cd.nq.gz
│   ├── 8dd04bcdb8113195a9624878de641fbc0ad044fa.nq.gz
│   ├── 936cc2501361e91cf706e0f4a6b4b57305d260bb.nq.gz
│   ├── 982acf8324573a22481d4ce2298e9ebc6166331d.nq.gz
│   ├── 9a0f3bce1395ae3819030b822e5d9076c85068ea.nq.gz
│   ├── c1656c3b2738bf30d98630d39a7093024405466a.nq.gz
│   ├── c38b791e93e9eef03966672f73a3e583fd28348b.nq.gz
│   ├── cb444e9e6caa80d54b81c5637c8aeb27c04a2c78.nq.gz
│   ├── d6c262d641ca9ee1ca78b87bebd8d383948ba31f.nq.gz
│   ├── e05a3d4a2ab888e32952006d8cd380864368db5f.nq.gz
│   ├── e42b16b73e987b5a34acb980eb47c8a061df2baf.nq.gz
│   ├── e61a5fd419c2ccfc3c1189bc258b3d57481d5dc1.nq.gz
│   ├── efcb8cbc2043faa7caf4f92fc7488bd6914c934c.nq.gz
│   └── fb59618eb0fae3e9323d1f255643e4f18c5d7921.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 68b1e2b1a77087b4058130e90e16169201ff4387.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 41 files
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

[jaraco/paradocx](https://github.com/jaraco/paradocx)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
