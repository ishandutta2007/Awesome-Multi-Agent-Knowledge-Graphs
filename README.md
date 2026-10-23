# Awesome-Multi-Agent-Knowledge-Graphs

# Awesome-Multi-Agent-Knowledge-Graphs

## Top Multi-Agent Knowledge Graphs Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Git-Style Agent Collaboration, Six-Layer Business Ontology & GraphRAG Retrieval*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Multi-Agent Knowledge Graphs**. These tools provide the shared, structured knowledge layer that multiple AI agents need to coordinate — storing entities, relationships, and observations in a graph that agents can query, traverse, and mutate, with governance controls to prevent the black-box problem where agents act on context no human can inspect.

**Examples** include Omnigraph, Neo4j Context Engine, TigerGraph, Palantir Foundry, and the emerging open-source graph tools (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, git-style branching for agent-generated changes, and transparent semantic schemas — ideal for teams building multi-agent systems where shared knowledge must be auditable, versioned, and governable.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Neo4j Context Engine](https://neo4j.com/)**  
  **The graph intelligence platform's dedicated answer to the agent knowledge problem** — launched October 2026 . **Six-layer business ontology** spanning business process, domain, data products, physical systems, tools/integration, and runtime knowledge — giving agents the meaning they lack when querying enterprise data . **Context Build and Runtime** connects physical data sources to business logic with governance and **GraphRAG retrievers** for accurate, cost-effective retrieval . **Memory and Learning** provides short-term, long-term, and reasoning memory in the same graph as business meaning, with **decision tracking** that logs agent reasoning paths as a permanent record . **Context Studio** provides a central control plane for managing the ontology, configuring agents, and monitoring the environment . **Best for enterprises** needing a governed, explainable knowledge layer for production agent fleets.

- **[TigerGraph](https://tigergraph.com/)**  
  **The enterprise graph platform with a dedicated Agentic AI stack** — **MCP Server** exposes graph capabilities as agent-accessible tools . **GraphRAG and hybrid retrieval** combine semantic similarity for unstructured content with relationship-aware retrieval for entities and dependencies . **Four architectural patterns** for graph in agent stacks: single agent with graph retrieval tool, multi-agent with shared graph memory, agentic RAG loop with graph as retrieval substrate, and MCP-connected agent with live graph access . **Savanna** provides cloud deployment with independently scalable storage and compute . **Best for enterprises needing real-time, parallel graph traversal** at scale for multi-agent coordination.

- **[Palantir Foundry](https://www.palantir.com/)**  
  **The enterprise platform whose Ontology is a semantic contract layer between raw data and applications/AI** — **not a database and not a traditional knowledge graph**. Defines **objects** (entities with primary keys and entity resolution), **properties** (attributes computed in real-time from underlying sources), **links** (business-semantic relationships with direction and permissions), and **actions** (write operations with validation, writeback, and transaction boundaries) . **Governance primitives** include granular access controls, purpose limitations, audit capabilities, and retention management . **The ontology is a two-way street** — IT feeds it from transactional systems and configures writeback actions that update source systems; end-user applications and AI agents trigger those actions . **Best for large enterprises** needing a governed semantic layer where AI decisions can change world state, with the caveat that it is proprietary and requires significant implementation investment.

## Open-Source GitHub Projects

- **[Omnigraph](https://github.com/ModernRelay/omnigraph)**  
  **The object-storage-native knowledge graph designed for agents and humans to collaborate** — Rust-based, built on Arrow, DataFusion, and Lance . **Git-style workflows for agent-generated changes**: branches, commits, merges, and transactional runs — so agent edits can be reviewed and merged safely rather than silently mutating shared knowledge . **Typed schema, typed queries, and typed mutations** with schema-as-code and query linting. **Native blob-as-data support** for docs, images, and videos. **Graph traversal plus text, fuzzy, BM25, vector, and RRF search in one runtime**. **Policy-as-code** for server-side access control. **S3-native storage with snapshot-pinned reads**. **Deploys as a cluster** managed Terraform-style with `cluster plan` and `cluster apply` . **Ships an agent skill** (`npx skills add ModernRelay/omnigraph@omnigraph`) covering cluster mode, schema evolution, query linting, data writes, branches, and Cedar policy . **Use cases**: company brain, agentic memory (a branch per agent or task), research knowledge base, incident response graph, compliance/audit graph . **Best for teams wanting git-governed shared knowledge** where agents and humans collaborate on a live graph with reviewable changes — the most agent-native open-source option.

- **[trikedb](https://pypi.org/project/trikedb/)**  
  **The file-based knowledge graph that ships as a single YAML file** — Python library with **SPARQL 1.1 support** via Oxigraph, **SHACL validation**, **RDFS/OWL inference**, and **hybrid semantic + structured retrieval** (`db.find("where is the customer CRM data?", where={"type": "table", "pii": True})`) . **MCP server with OAuth 2.1** — `trikedb serve graph.yaml --oauth-issuer https://idp.example.com/` turns the graph into an MCP resource server that verifies tokens against your IdP without issuing them . **Eleven MCP tools** shared across stdio and HTTP transports . **The ontology acts as a guardrail** — undeclared predicates raise `OntologyError` rather than silently landing typos . **Provenance tracking** via a standardized `prov` attribute on facts. **Exports to HTML** with searchable graph and in-browser SPARQL console, plus RDF, JSON-LD, and NetworkX views . **The entire graph is a human-readable YAML file** that autosaves on mutation . **Best for teams wanting a lightweight, file-native knowledge graph** with real RDF/SPARQL semantics, SHACL validation, and MCP integration without a database server.

### Additional Strong Open-Source Options

- **docsiq** — GraphRAG-powered knowledge base as a single Go binary. Ingests documents, builds a knowledge graph with **pure-Go Louvain community detection**, persists wikilinked markdown notes, and exposes everything over **MCP** plus an embedded React SPA on one port. **SQLite with FTS5 and sqlite-vec** for vector search. **Three LLM providers** with a `provider: "none"` mode for notes-only operation . **Best for teams wanting a lightweight, single-binary knowledge graph** with MCP tooling for agents.
- **Neo4j Community** — The open-source graph database core. **Context Engine and MCP Server are commercial**, but the graph engine and Cypher query language are available for self-hosted multi-agent memory implementations.
- **Apache AGE** — PostgreSQL extension adding graph database functionality, enabling relationship queries within existing Postgres infrastructure.

**Frameworks for building custom systems**: Combine **Omnigraph** for git-governed shared knowledge with branch-based agent collaboration and S3-native storage, **trikedb** for a file-native knowledge graph with SPARQL/SHACL semantics and MCP tools, **docsiq** for a lightweight single-binary GraphRAG knowledge base with MCP, and **Neo4j Context Engine** or **Palantir Foundry** if you need a fully governed enterprise semantic layer with action execution and dynamic policy — to build a multi-agent knowledge graph stack tailored to your governance requirements, storage preferences, and agent collaboration model.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Multi-agent knowledge graph tools differ significantly in governance model, storage architecture, and agent integration. **Omnigraph's git-style branching is uniquely agent-native** — agents create branches for proposed changes rather than mutating shared knowledge directly, enabling human review before merge . **Palantir Ontology is not a knowledge graph** in the traditional sense — it's a semantic contract layer with actions that change world state, and the difference matters when evaluating whether you need read-only analysis or writable governed behavior . **Neo4j Context Engine's six-layer ontology** is the most comprehensive enterprise offering, but it is commercial and requires the Neo4j Graph Intelligence Platform . **trikedb stores the entire graph in a YAML file** — ideal for small-to-medium graphs but not designed for petabyte-scale enterprises . **GraphRAG is not a solved problem** — entity resolution and relationship inference remain open challenges in production knowledge graphs . **Multi-agent shared memory without governance is a liability** — agents that can silently mutate shared knowledge create audit and correctness problems that branching and policy controls are designed to prevent.
- Self-hosted open-source solutions require proper S3-compatible storage for Omnigraph, schema design for typed queries, and policy definition before agents are granted write access.

---

**Made for AI engineers and platform teams building governed, auditable shared knowledge for multi-agent systems.**
Let's make multi-agent knowledge graphs more open, version-controlled, and collaboration-safe.
