# Repolex Knowledge Graph of pydantic/logfire-mcp

RDF knowledge graph data for [pydantic/logfire-mcp](https://github.com/pydantic/logfire-mcp), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/logfire-mcp
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1e11c2ce193050a11fc956151a2adc78966518c1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1e11c2ce193050a11fc956151a2adc78966518c1
│           └── chunk-001.nq.gz
├── blob
│   ├── 1243aaba76d622b82862a508122912e416b8008b.nq.gz
│   ├── 2029441393484d19a2b8fa02ffcf132f15249279.nq.gz
│   ├── 3225fe5a48300e77cbe4ae5853de8ab0900af963.nq.gz
│   ├── 3f674462342f2872f3a390f8352e335b005e18fa.nq.gz
│   ├── 5a7556ce5dba0565b7ec2f4454c4d68951476164.nq.gz
│   ├── 7773766fd73aa8833b430ccebf6d154525be461f.nq.gz
│   ├── 7980bc87ae6ad1fdf87f58244533819cb9a398ba.nq.gz
│   ├── 7c03240df890d2369cf040a36a1e1569f6f3f149.nq.gz
│   ├── 7e1c97658e58960d70ffcea9971600e07888fc40.nq.gz
│   ├── a6d67e80ffa3a83ab264bdbe9c624d9a50c7689f.nq.gz
│   ├── afeecbfddc89b7082b2281bfd8266157e1580a25.nq.gz
│   ├── b13076812729a23107d6338e483ea9906d479617.nq.gz
│   ├── b3feb9998d40a14e4915e447da351d76ff48d811.nq.gz
│   ├── ca16eabe9a4c37d9f418f7ea3e711a03aab75b2d.nq.gz
│   ├── cbfd3fc59ee38acc062f0e0d8d8be2d8b34d7395.nq.gz
│   ├── e4fba2183587225f216eeada4c78dfab6b2e65f5.nq.gz
│   ├── e599167b5f7edf325936575abda655e63d7857fd.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e920ab32c4acd5e08b17373509514e8ea947be2c.nq.gz
│   ├── e931a3499413e5c459fbfa412f4510143f71d6ba.nq.gz
│   ├── ead888797579f21513655c1a5b055028f4f2fb77.nq.gz
│   ├── f46ca48831f12a0d24107d92a2d6572913345f4d.nq.gz
│   └── ff434b8cea7c582986ac94e8cde943717882f3a6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1e11c2ce193050a11fc956151a2adc78966518c1.nq.gz
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

[pydantic/logfire-mcp](https://github.com/pydantic/logfire-mcp)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
