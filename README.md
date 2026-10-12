# Repolex Knowledge Graph of Pylons/pyramid_simpleform

RDF knowledge graph data for [Pylons/pyramid_simpleform](https://github.com/Pylons/pyramid_simpleform), parsed by [repolex](https://repolex.ai).

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
rlex download Pylons/pyramid_simpleform
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 30c666418c7d344c01b77a63ee2d78a60cd852cb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 30c666418c7d344c01b77a63ee2d78a60cd852cb
│           └── chunk-001.nq.gz
├── blob
│   ├── 00199ae6e9a07615fa3955b76a13083da24ff8f7.nq.gz
│   ├── 01a53b714213d09292698680057436712c32a680.nq.gz
│   ├── 0c4326de18adc601238a473d390290b591952263.nq.gz
│   ├── 0cf548c51ce8ddb4ced53827fa262098d8d66fc9.nq.gz
│   ├── 142b6ca357fee89f09803fc9ad7ff676500c37cf.nq.gz
│   ├── 1cda9f55b1d1344cb34fb4310518772d68f5aeac.nq.gz
│   ├── 29539c6b5bc3f506085949e84aa595b580146d66.nq.gz
│   ├── 2a3efd761d71f4568e7327b3a367b53dac2d7b31.nq.gz
│   ├── 35a34f33241b3255e30ce34cd0efed3b534f9171.nq.gz
│   ├── 3974ecfd3d9c0e029d0fd8f1aa6a589895f39fb1.nq.gz
│   ├── 42258cc4a42c682b6d5f9beac2b9795c9c201367.nq.gz
│   ├── 49d0cc490109843aae37aca1354bf8928cd0f658.nq.gz
│   ├── 570a2c42987485be02c724afdc4c39542ea25a12.nq.gz
│   ├── 57cfde92b3eac7b04f58fb3e7ac5a3b511e5503a.nq.gz
│   ├── 5e4090017a9bec5de60a745d17007a9e95f31a43.nq.gz
│   ├── 65942c3d14f04b75a94c10c920a186fa9884bd10.nq.gz
│   ├── 687052866957340b69ad4f3e0dab896bb8632f06.nq.gz
│   ├── 71f837c9e27a57cc290a775b8260241d456582e9.nq.gz
│   ├── 747b2452996e6ef3d956233e15a23419fefeb375.nq.gz
│   ├── 7e164783755d6848a0324bcb317bea2564bcaa58.nq.gz
│   ├── 8856e7840aa64884959fbfe2e3f36b8cbf3ed832.nq.gz
│   ├── 88b3708f39090a2cabeb44ba505cb97351b37de4.nq.gz
│   ├── 88f5d9865673404414b505011d71aad2f829ce67.nq.gz
│   ├── 902627b31c12970c65b396be538fe305a23aff68.nq.gz
│   ├── 98c999dea7d956645c0007739005f1e6cd66ae29.nq.gz
│   ├── ada940ffaa919215be9eedae6078fd6f9ca86761.nq.gz
│   ├── b8844a380e228b88f224e09c43517272c9bc1845.nq.gz
│   ├── b982c9e0bd3c63fb10458c4a873ebd01e858b498.nq.gz
│   ├── bbab79a53029e9c543031b86aaa8b428854203bb.nq.gz
│   ├── c2d7766a2e0ab6e7194244a2e5aca77d8663960b.nq.gz
│   ├── c9a8c9d34f81e7ce4334f939034e55f1a3aa8c75.nq.gz
│   ├── caa82806bd06e6e68cee63597da2ebb0da0fbed3.nq.gz
│   ├── cb03207a8b897ae9a5666f24561a0c4ba67560f3.nq.gz
│   ├── e429fb7319397930be49192a27229ad9f7beaa6b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea27efca8240af60e5b4ed44d749ed6b23af28b5.nq.gz
│   ├── ea61463a22bfeea192b3985943507ac30765b360.nq.gz
│   └── ee1c3305eddf1b3bf8a37c4bbf0f5714e1baab54.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 30c666418c7d344c01b77a63ee2d78a60cd852cb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[Pylons/pyramid_simpleform](https://github.com/Pylons/pyramid_simpleform)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
