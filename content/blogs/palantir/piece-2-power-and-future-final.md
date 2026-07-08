---
title: "The Same Machine: Service or Surveillance?"
description: "A reflective note on how the same operational data layer can support public service or become infrastructure for classification and surveillance."
date: 2026-07-08
draft: false
url: "/persona/service-or-surveillance/"
translationUrl: "/zh/persona/service-or-surveillance/"
translationLabel: "中文"
translationCta: "Read in Chinese"
series: ["Persona"]
tags: ["Governance", "Data Boundaries", "Surveillance"]
build:
  list: never
  render: always
---

# The Same Machine: Service or Surveillance?

The previous piece told a rather uplifting story: a system that got farmers billions in aid within 62 minutes.

This piece is about the flip side of that same story.

Because the very same capability — folding scattered identities, assets, relationships, histories, and risk signals into one computable web of objects — becomes, with a change of purpose, a map for scoring people, locating them, and deciding who gets prioritized and who gets watched. It isn't that the machine turned bad. It's that it was always the same machine.

## First, a splash of cold water: the cost

Before the risks, be clear that this is no free lunch.

Building a "model of reality" like this is heavy and expensive, and it's fundamentally not a technology project — it's an organizational restructuring. Because first you have to answer a pile of questions with no standard answers: what counts as "the same person"? What counts as "one event" — by which definition, and where do you draw the boundary? What counts as "high risk"? These definitions are full of institutional politics and power.

And here's the crucial part: once those definitions are written into the system and run automatically, power quietly concentrates in the hands of whoever can change that layer. Definition is power.

## The real danger isn't "seeing" — it's "classifying + intervening"

When we talk about privacy, we picture "is it looking at my data?" But the real power of a modern data system lies not in *seeing* but in *classifying*.

It sorts people into: high risk / low risk, trustworthy / suspect, prioritize / defer, auto-approve / needs human review, worth the resources / potentially high-cost. And once that classification enters a workflow, it directly reshapes how real resources get allocated — who gets seen first, who gets enrolled into management, whose situation gets changed.

So the crucial question was never "is the system looking at my data?" It's: **how does the system define me? Does that definition affect the services I can get? Can I know, challenge, and correct it?**

There's an even quieter mechanism at work, called *mission creep*: data collected for one purpose later gets repurposed for something entirely different.

This isn't hypothetical. Two real anchors (both from public reporting; verify details against the latest sources):

One is the U.K. The National Health Service built a unified data platform connecting patient and operational data across organizations — logic almost identical to the agency's "one farmer, one file." Officials stress that the data remains the NHS's, that the vendor is only a processor, and that access is controlled. Yet clinicians, lawmakers, and advocacy groups keep pressing: is there adequate public consent? Who can actually see identifiable patient data?

The other is the U.S. According to reporting, immigration enforcement has used a tool wired into Medicaid and other data to generate dossiers, addresses, and "confidence scores" on people who may be deportable, for targeting purposes; the underlying data-sharing reportedly covers tens of millions of enrollees. Data collected to get people care flowed, this way, toward enforcement.

I'll admit that since I now work with health data myself, a story like "data collected for care flowing toward enforcement" lands harder on me than an ordinary headline — because I know how intimate that data is, and I know that the moment people fear it'll be used this way, they start avoiding the doctor.

## So what's the deciding variable?

Governance, not technology.

The same capability, used for issuing subsidies and checking eligibility, means less paperwork and faster payments. Used for scoring and locating, it means surveillance. The technology itself is neutral. What actually decides which way it goes are the questions that sit *outside* the technology: who can access it? Can the data be used across purposes? Can the person know, appeal, and correct a wrong label?

So you can't judge a system like this only by the good it does today; you also have to ask what it makes *easy*. Once the capability exists, the boundaries of its use become a political question, not an engineering one.

## Is it, then, a necessary path for every enterprise?

A natural next question: if this layer is so pivotal, must every large institution that wants AI build it?

My take: split the question in two.

*Some* kind of "governed reality layer" is increasingly unavoidable for institutions that want AI to actually *do* things rather than just chat — and that's largely become a consensus in the field. But "it must be one specific vendor's full-blown ontology" or "you must model the entire organization exhaustively" simply doesn't hold.

The more accurate framing: this is not a single gate everyone queues to pass through — it's a gradient. **The more your AI moves from *talking* to *doing*, and from *personal tool* to *organizational operation*, the more it's pulled toward some governed reality layer.** Whether it's called an ontology, a semantic layer, or something else, and how deep it goes, and whose product it is — those vary enormously. The rational move is to build this layer only around your highest-risk, most accountability-sensitive core, and let lighter approaches suffice everywhere else.

## A question to sit with

Put the two pieces together and they're two faces of one thing: the clarity that gets a farmer paid early, and the clarity that gets a person precisely located, are the *same* clarity.

So the thing worth thinking about, in the end, isn't "is this company good or bad?" It's this set of questions:

When a system can define "who you are" and "whether you're high-risk," and route resources accordingly — **who defines that model? Who owns it? Who can change it? And once it classifies you, can you know, and can you appeal?**

The competition of the future may turn not on who wires up a model fastest, but on who can build reality most clearly, most controllably, most trustworthily. But don't forget: the capability to build reality that clearly is the very same capability to classify and intervene on people. So what truly deserves open debate was never how powerful the technology is — but who uses it, and under what rules.
