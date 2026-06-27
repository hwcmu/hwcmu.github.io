---
title: "Persona"
description: "Reflective notes, tags, and search for how I think and work."
hideMeta: true
url: "/persona/"
---

<div class="page-hero tone-persona">
  <div class="page-icon persona-icon"><svg viewBox="0 0 48 32" aria-hidden="true"><path class="mask-left" d="M23.5 9.5c-4.8-3.2-10-4.5-18-2.3-1.4 8.1 1.2 15.3 7 17.1 5 1.5 9.8-2.5 11-8.7z"/><path class="mask-right" d="M24.5 9.5c4.8-3.2 10-4.5 18-2.3 1.4 8.1-1.2 15.3-7 17.1-5 1.5-9.8-2.5-11-8.7z"/><path d="M16 15.5c1.5-.7 3-.7 4.5 0M27.5 15.5c1.5-.7 3-.7 4.5 0M22.6 22c.9.7 1.9 1 2.9 0"/></svg></div>
  <div>
    <p class="eyebrow">Reflective layer</p>
    <p class="lead">A lighter space for work style, taste, questions, and small patterns behind the research pages. Less formal than Papers, more inward-facing than Notes.</p>
    <div class="chip-row persona-tags" aria-label="Filter persona entries">
      <button class="chip persona-tag active" type="button" data-tag="all">All</button>
      <button class="chip persona-tag" type="button" data-tag="work">Work style</button>
      <button class="chip persona-tag" type="button" data-tag="writing">Writing</button>
      <button class="chip persona-tag" type="button" data-tag="tools">Tools</button>
      <button class="chip persona-tag" type="button" data-tag="questions">Questions</button>
    </div>
  </div>
</div>

<div class="persona-search">
  <label for="persona-search-input">Search Persona</label>
  <input id="persona-search-input" type="search" placeholder="Search reflections, tags, or themes..." autocomplete="off">
</div>

<div class="persona-list" id="persona-list">
  <article class="persona-entry" data-tags="work questions" data-text="question first work style research boundaries clinical data collaboration">
    <span class="series-kicker">Work style</span>
    <h3>Question first, method second</h3>
    <p>I am usually more interested in the sentence a model is allowed to support than in the model itself. Good analysis starts when the claim, timing, and data boundary are visible.</p>
  </article>
  <article class="persona-entry" data-tags="writing questions" data-text="writing careful claims reviewers evidence interpretation boundaries">
    <span class="series-kicker">Writing</span>
    <h3>Careful claims age better</h3>
    <p>I like prose that shows its limits. A restrained sentence can be more useful than a dramatic one when readers need to understand what evidence can and cannot say.</p>
  </article>
  <article class="persona-entry" data-tags="tools work" data-text="tools reproducible workflow scripts notebooks audits local files">
    <span class="series-kicker">Tools</span>
    <h3>Tools are memory for decisions</h3>
    <p>Scripts, notebooks, and checklists are not just automation. They are a way to preserve why a choice was made, so future review is less dependent on memory.</p>
  </article>
  <article class="persona-entry" data-tags="questions writing" data-text="questions reflective notes ambiguity collaboration research judgment">
    <span class="series-kicker">Questions</span>
    <h3>The useful ambiguity</h3>
    <p>Some uncertainty should be resolved with code or evidence. Some should be kept visible because it marks where judgment, audience, or ethics still matter.</p>
  </article>
</div>

<p class="persona-empty" id="persona-empty" hidden>No matching reflections yet.</p>
