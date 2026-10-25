---
title: "The Same Layer: Service and Governance (2/3)"
description: "A note on the definitions, access rules, and review paths needed for an operational data layer."
date: 2026-07-08
draft: false
personaKicker: "Essay · Palantir Notes"
url: "/persona/service-or-governance/"
translationUrl: "/zh/persona/service-or-governance/"
translationLabel: "中文"
translationCta: "Read in Chinese"
series: ["Persona"]
tags: ["Governance", "Data Boundaries", "AI Systems"]
build:
  list: never
  render: always
---

The first piece described how shared definitions can reduce repeated reconciliation in a service workflow. That benefit depends on a second question: how are those definitions maintained and used?

An operational layer links records, relationships, and permitted actions. The links may help a team process a request consistently, but they also determine what the system can infer and which steps it can automate. Both effects need review.

## Definitions need owners

Building this layer takes more than connecting tables. A team must decide when two records refer to the same object, what counts as one event, and which source takes precedence when records disagree. Those choices affect later reports and actions.

Each definition therefore needs an owner, a documented change process, and a way to correct errors. A shared model makes decisions easier to reuse; it does not make the underlying records complete or certain.

## Access and use need separate rules

Access control asks who may read or change a record. A purpose rule asks what a workflow may do with it. A useful review checks both, along with the path for a person or team to identify and correct an error.

Data collected for one workflow may later be considered for another. Before reuse, the team should document the new purpose, check that it is permitted, and review whether existing access and retention rules still fit. These are ordinary design and governance questions, not evidence that any particular platform has misused data.

## What should be checked before an action runs?

For each automated step, define the input, allowed change, validation rule, approver when needed, and record of the decision. Technical controls and organizational review work together. Neither follows automatically from naming a system an ontology.

The level of control should match the consequences of the action. A read-only summary and a change to a source system need different safeguards. A model that proposes a change can be kept separate from the service that applies it.

## How much shared infrastructure is enough?

There is no single required product or exhaustive model for every organization. A small workflow may need only stable identifiers and clear review steps. More consequential actions may need stronger permissions, validation, and monitoring.

The practical question is whether the definitions and controls are sufficient for the specific workflow. Who maintains them? How are errors found? What happens when a source changes? What can the system do automatically, and what requires review? Those answers matter more than a broad claim that the platform is either safe or unsafe.
