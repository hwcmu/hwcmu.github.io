---
title: "The Gate Between Knowing and Doing (3/3)"
subtitle: "An operational ontology can help define how software and AI read data and propose actions."
description: "A technical companion on operational ontologies, entity resolution, governed actions, and the boundary between AI-generated suggestions and real-world execution."
date: 2026-07-11
draft: false
personaKicker: "Essay · Palantir Notes"
url: "/persona/between-knowing-and-doing/"
translationUrl: "/zh/persona/between-knowing-and-doing/"
translationLabel: "中文"
translationCta: "Read in Chinese"
series: ["Persona"]
tags: ["Ontology", "AI Systems", "Governance"]
build:
  list: never
  render: always
---

The first two pieces asked what an operational ontology makes possible and what kinds of governance questions follow. This final piece looks inside the machinery. The important shift is not from a small model to a larger one. It is from software that can describe an organization to software that can act inside a deliberately bounded version of it.

## Where an ontology sits

A database is primarily a storage layer. A semantic layer stabilizes metrics and definitions. A knowledge graph represents entities and relationships. An operational ontology can add state, permitted actions, permissions, and audit features.

That distinction matters because an ontology is not a magical file format containing the whole organization. It is a layer of definitions, services, and code placed over ordinary data storage. In the Foundry model, the stack can be understood in four parts:

- **Storage:** standard datasets hold records drawn from source systems.
- **Definitions:** object types, links, actions, and functions state what the records mean.
- **Serving:** indexed objects support fast queries and controlled write-backs.
- **Typed interfaces:** SDKs expose objects and actions to applications without making every developer work directly with raw tables.

The formal-ontology tradition is older than current AI platforms. RDF, OWL, and SPARQL were built to represent shared concepts and relationships; healthcare has long pursued similar goals through SNOMED CT, ICD, LOINC, RxNorm, and common data models such as OMOP. The newer operational move is to connect those definitions to actions.

## The action layer

An action type can specify which object it applies to, which inputs it accepts, what it may change, which conditions must hold, and who may invoke it. Approval and decision logging require explicit configuration.

When an action runs, a well-configured workflow records the edit and its context. Direct writes and external side effects need separate checks; an action log alone does not cover every path. This is where the ontology can become an operating boundary rather than only a map.

For AI, that boundary is more useful than a broad instruction to "be safe." A model can be allowed to draft a recommendation while being denied authority to execute it. It can call a predefined action but cannot invent a new kind of write. Higher-risk actions can require human approval.

This does not eliminate model error. It narrows what an error can reach.

## Entity resolution comes first

Before objects can support actions, the system has to decide which records refer to the same real-world thing. Across many source systems, there may be no shared key. In healthcare, this is the familiar patient-matching or Master Patient Index problem.

Deterministic matching works when a reliable identifier is available. Probabilistic matching is needed when records must be compared using several imperfect fields. A typical pipeline looks like this:

1. Standardize and clean the source fields.
2. Use blocking rules to reduce the number of candidate comparisons.
3. Score candidate matches.
4. Automatically resolve clear cases and route ambiguous cases for review.
5. Apply survivorship rules when sources disagree.
6. Assign a durable identity while preserving lineage back to the source records.

There is no perfect threshold. A false merge treats two people as one; a false split treats one person as two. The costs differ by workflow, so the threshold is not merely a technical setting. It encodes a decision about which mistakes the organization is more prepared to tolerate.

## Two channels for an AI system

The architecture becomes easier to understand when reading and writing are treated as separate channels.

**The read channel** retrieves structured, permission-aware objects with source lineage. If relevant information is absent, the system should expose that absence instead of filling it with a plausible detail. The model may still reason poorly, but its factual inputs can be inspected.

**The write channel** can limit the model to predefined actions. Validation, permissions, approval rules, and audit logs must be configured around a generated suggestion before it becomes a real change. This separation narrows the model's authority when direct write paths are also controlled.

The technical goal is modest but important: a wrong model output should not automatically become an unconstrained operational act.

## A clinical example

Consider a hypothetical analysis question: did a qualifying encounter occur within 180 days after a defined index event?

In an ordinary analysis pipeline, an analyst defines the cohort, index date, observation window, censoring rules, encounter codes, and deduplication logic in SQL or another transformation layer. The result can be rigorous, but the meaning often remains embedded in project-specific code.

A RAG-plus-SQL assistant can translate a natural-language question into a query, but it still has to infer which date is the index and what counts as a qualifying encounter. Similar field names may refer to different steps in a workflow. A syntactically valid query can therefore return a plausible number with the wrong meaning.

In an ontology-based approach, the temporal definition can be attached to a reusable episode object. The index event, follow-up window, censoring event, and qualifying encounter are explicit properties rather than assumptions reconstructed for every query. An agent may read those governed objects and, where appropriate, create a review recommendation. Any change to a source system still needs a separately defined and tested action path.

The dividing line is not natural language versus SQL. It is whether the semantics and permitted actions live in reusable, reviewable infrastructure.

## MCP is not the ontology

Function calling defines an interface for invoking a tool. MCP provides a protocol for connecting models to tools and resources. An operational ontology can define what the linked records mean and which actions a workflow exposes.

A protocol can connect a model to a database without telling it which field represents a clinical event, which is a billing artifact, or which encounter establishes the index date. Connectivity supplies access. The ontology supplies a governed interpretation.

## The maturity ladder is also a responsibility ladder

It is tempting to describe AI systems as a neat progression:

- L1: chatbot
- L2: retrieval assistant
- L3: tool-using agent
- L4: workflow agent with confirmation
- L5: ontology-based operational agent

But each step adds responsibility as well as capability. The closer a system moves from answering to acting, the more it needs stable definitions, narrow permissions, visible uncertainty, review paths, and durable audit records.

That is the technical conclusion of the series. The ontology matters not because it makes an AI sound more informed, but because it gives an organization a place to decide what the AI is allowed to know, what it is allowed to propose, and where it must stop.

## Sources

- [Palantir Foundry: Action type permissions](https://www.palantir.com/docs/foundry/action-types/permissions)
- [Palantir Foundry: Action logs](https://www.palantir.com/docs/foundry/action-types/action-log)
- [Palantir Foundry: Action webhooks](https://www.palantir.com/docs/foundry/action-types/webhooks)
