---
title: "Persona"
description: "Reflective notes, tags, and search for how I think and work."
hideMeta: true
url: "/persona/"
---

<div class="page-hero tone-persona">
  <div class="page-icon persona-icon"><svg viewBox="0 0 64 40" aria-hidden="true"><path class="mask-left" d="M30.8 6.8C22.2 1.9 12.7 4 5.5 9.7 4.1 20.5 9.7 31.5 20 32.6c6.3.7 9.8-5.8 10.8-14.1z"/><path class="mask-right" d="M33.2 6.8C41.8 1.9 51.3 4 58.5 9.7c1.4 10.8-4.2 21.8-14.5 22.9-6.3.7-9.8-5.8-10.8-14.1z"/><path class="mask-split" d="M32 7.4v25.4"/><path class="mask-eye-left" d="M15.2 17.2c2.3-1.3 5-1.3 7.3 0"/><path class="mask-eye-right" d="M41.5 17.2c2.3-1.3 5-1.3 7.3 0"/><path class="mask-mouth-left" d="M25.4 24.7c1.9 1.2 3.8 1.2 5.3 0"/><path class="mask-mouth-right" d="M33.3 24.7c1.5 1.2 3.4 1.2 5.3 0"/></svg></div>
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
