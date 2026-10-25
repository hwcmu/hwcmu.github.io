---
title: "An Operational Map: Connecting Records to Actions (1/3)"
description: "A reflective note on how an operational ontology can connect records, relationships, and defined actions."
date: 2026-07-05
draft: false
personaKicker: "Essay · Palantir Notes"
url: "/persona/activated-map/"
translationUrl: "/zh/persona/activated-map/"
translationLabel: "中文"
translationCta: "Read in Chinese"
series: ["Persona"]
tags: ["Ontology", "AI Systems", "Data Integration"]
build:
  list: never
  render: always
---

A technology talk about connecting fragmented records into an operational model stayed with me. It raised a practical question: what changes when a workflow can use shared definitions of objects, relationships, and actions?

Consider a common integration problem. Records sit in different systems, each with its own identifiers and definitions. Connecting them can reduce the reconciliation needed for a service request, provided the mappings are accurate and maintained.

The useful idea is to define what the records refer to before asking software or AI to act on them.

The more I sat with it, the clearer it became that this was not really about one sector at all. It's the problem that any field tangled up in "too many systems, all speaking past each other" eventually has to face.

## A database stores *records*, not *reality*

We tend to assume the data is already sitting in databases, so surely you just connect it? The trouble is that a database stores *records*, not *reality*.

Think of a large institution as a library where different departments write their own books. Finance uses one identifier for a record; another office uses a different one. Without a reliable mapping, a workflow may not know whether those records refer to the same object. I have seen versions of this problem in data work: one object can have several IDs that do not line up automatically.

A data warehouse can bring records together, but storage in one place does not by itself reconcile conflicting identifiers or definitions. Teams may also use master-data management, matching rules, and manual review. The ongoing work is to document how records correspond and how exceptions are handled.

## An ontology: an activated map you can act on

An ontology does something different: on top of those underlying records, it builds an *activated map*.

That map holds three things — objects (such as an asset or a request), relationships (how those objects connect), and actions (such as moving a request to its next step). It can link records from different systems to a shared object while keeping their source and uncertainty visible.

Pay special attention to that last word, *actions*. An operational ontology can expose permitted changes as defined actions rather than leaving every workflow to write directly to a source table. Permissions, approval steps, and decision logs still have to be configured and checked; the ontology alone does not guarantee them.

## Why it's powerful: four advantages

First, shared definitions can reduce repeated mapping work. A new workflow may reuse an existing object model, though changes in source data and business rules still need maintenance.

Second, relationships can be made explicit and reusable. A workflow can follow a defined link between an object and a request, while retaining the ability to inspect how that link was established.

Third, predefined actions can connect analysis to an operational workflow. Whether AI may invoke them, and under what review, is a separate design choice.

Fourth, a shared layer can sit over existing systems without requiring all of them to be replaced. It still depends on integration work and on the quality of those source systems.

## But won't the AI go rogue?

There is no automatic guarantee. A system can restrict an AI assistant to permission-aware reads and predefined actions, require approval for consequential changes, and record decisions for review. Those controls narrow what an error can reach when they are correctly configured and tested. Missing data can still lead to a wrong answer, and an allowed action can still have an unintended effect. (The mechanics are the subject of the third piece in this series.)

## A question to sit with

The thing worth pausing on is why "integrating the data" can remain difficult even after substantial investment.

Technology and organizational definitions both matter. An organization has to decide which objects a workflow uses, how they relate, who maintains each definition, and how disputed records are corrected. An ontology makes those choices explicit enough to inspect and revise.

The next piece asks how an organization should govern those definitions and the actions built on them.
