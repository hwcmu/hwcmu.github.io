---
title: "The Same Machine: Service or Governance? (2/3)"
description: "A reflective note on how the same operational data layer can support better service while raising governance and data-use boundary questions."
date: 2026-07-08
draft: false
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

The previous piece told a rather optimistic story: a fragmented service workflow became dramatically faster once the underlying objects and actions were modeled clearly.

This piece is about the flip side of that same story.

Because the very same capability — folding scattered identities, assets, relationships, histories, and risk signals into one computable web of objects — becomes, with a change of purpose, a map for classification, prioritization, and operational intervention. It is not that the machine suddenly changes nature. It is that the same capability can serve very different institutional purposes.

## First, a splash of cold water: the cost

Before the risks, be clear that this is no free lunch.

Building a "model of reality" like this is heavy and expensive, and it's fundamentally not a technology project — it's an organizational restructuring. Because first you have to answer a pile of questions with no standard answers: what counts as "the same person"? What counts as "one event" — by which definition, and where do you draw the boundary? What counts as "high risk"? These definitions are full of institutional politics and power.

And here's the crucial part: once those definitions are written into the system and run automatically, power quietly concentrates in the hands of whoever can change that layer. Definition is power.

## The real issue is not only "seeing" — it is "classification + intervention"

When we talk about privacy, we picture "is it looking at my data?" But the real power of a modern data system lies not in *seeing* but in *classifying*.

It sorts people into: high risk / low risk, trustworthy / suspect, prioritize / defer, auto-approve / needs human review, worth the resources / potentially high-cost. And once that classification enters a workflow, it directly reshapes how real resources get allocated — who gets seen first, who gets enrolled into management, whose situation gets changed.

So the crucial question was never "is the system looking at my data?" It's: **how does the system define me? Does that definition affect the services I can get? Can I know, challenge, and correct it?**

There is an even quieter mechanism at work, often called *mission creep*: data collected for one purpose later gets reused for a purpose the original subjects did not expect. In high-trust service settings, this can become especially delicate because the data is intimate, the people affected may be vulnerable, and the consequences of a wrong label can be hard to unwind.

The U.K. National Health Service's Federated Data Platform is a useful public example here. Its stated goal is to connect patient and operational data across NHS organizations so planning, coordination, and care delivery can work better. NHS England has described the data as remaining under NHS control, with vendors acting as processors and access governed by controls. At the same time, public debate around the platform has focused on consent, transparency, access to identifiable patient data, and how much the public understands about the system's boundaries. That is exactly the kind of case where the technical question and the trust question cannot be separated.

That is why I find the governance question more important than the vendor question. If a platform connects records across institutions, the public-facing issue is not only whether the system is efficient. It is whether the purpose boundary is explicit, whether access is narrow, whether identifiable data is protected, and whether affected people have a realistic path to understand and correct decisions that touch them.

## So what's the deciding variable?

Governance, not technology.

The same capability, used for processing service requests and checking criteria, means less paperwork and faster response. Used without clear boundaries, it can become classification infrastructure that people cannot easily see or challenge. The technology itself is neutral. What actually decides which way it goes are the questions that sit *outside* the technology: who can access it? Can the data be used across purposes? Can the person know, appeal, and correct a wrong label?

So you can't judge a system like this only by the good it does today; you also have to ask what it makes *easy*. Once the capability exists, the boundaries of its use become a political question, not an engineering one.

## Is it, then, a necessary path for every enterprise?

A natural next question: if this layer is so pivotal, must every large institution that wants AI build it?

My take: split the question in two.

*Some* kind of "governed reality layer" is increasingly unavoidable for institutions that want AI to actually *do* things rather than just chat — and that's largely become a consensus in the field. But "it must be one specific vendor's full-blown ontology" or "you must model the entire organization exhaustively" simply doesn't hold.

The more accurate framing: this is not a single gate everyone queues to pass through — it's a gradient. **The more your AI moves from *talking* to *doing*, and from *personal tool* to *organizational operation*, the more it's pulled toward some governed reality layer.** Whether it's called an ontology, a semantic layer, or something else, and how deep it goes, and whose product it is — those vary enormously. The rational move is to build this layer only around your highest-risk, most accountability-sensitive core, and let lighter approaches suffice everywhere else.

## A question to sit with

Put the two pieces together and they're two faces of one thing: the clarity that makes a service workflow faster, and the clarity that makes a person easier to classify, are built from the *same* kind of operational clarity.

So the thing worth thinking about, in the end, is less "is this company good or bad?" and more this set of questions:

When a system can define "who you are" and "whether you're high-risk," and route resources accordingly — **who defines that model? Who owns it? Who can change it? And once it classifies you, can you know, and can you appeal?**

The competition of the future may turn not on who wires up a model fastest, but on who can build reality most clearly, most controllably, most trustworthily. But that clarity needs rules around it. What deserves open discussion is not only how powerful the technology is, but who can use it, for what purpose, and with what safeguards.
