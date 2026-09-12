---
theme: apple-basic
addons:
  - slidev-addon-bluesky
title: The Frontend City
layout: intro
class: grid
transition: slide-left
comark: true
---
<!-- markdownlint-disable -->

# Workshopping Ember with Storybook

Thomas Gossmann

<lucide-house /> <a href="https://gos.si" target="_blank">gos.si</a><br>
<simple-icons-bluesky /> <a href="https://bsky.app/profile/gos.si" target="_blank">gos.si</a><br/>
<simple-icons-github /> <a href="https://github.com/gossi" target="_blank">gossi</a><br>

---

# Agenda

- Problem Statement
- Intro / Workshop Metaphor / What tools?
- Storybook: Hokulea
  - Installation and Config w/ Ember App and Owner
  - Stories (writing them, using the controls)
  - Docs mode
  - Decorators and global Args
  - MCP?
- Sportipedia
  - Setup for Sportipedia
  - Composition in hokulea
  - API docs
  - MSW
  - Routes
  - Playing
- Tests
- Visual Regression Testing
- Thanks

---

# Problem Statement

My Project: [Sportipedia](https://github.com/gossi/sportipedia)

I was figuring out the tooling how I want to work on that project for the last year

- Architecture: Hybrid of Vertical Slice + Clean Architecture to support the Domain
- Backend: Elixir, Commanded, EventSourcingDB
- Authentication: Better-auth
- Agents: ESDM
- Frontend:
  - Ember on vite + Warp Drive
  - Design System: [Hokulea](https://github.com/hokulea/hokulea)

... Testing?


---

# Workshop?

<figure class="absolute right-8 top-10" style="width: 44%" v-click>
  <img src="/adam-patterson-workshop.jpg" alt="brown wooden table with white printer papers">

  <figcaption class="font-size-2 text-right">
  By <a href="https://unsplash.com/de/@adampatterson?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Adam Patterson</a> on <a href="https://unsplash.com/de/fotos/brauner-holztisch-mit-weissem-druckerpapier-v13x0qU4afA?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  </figcaption>
</figure>

<figure class="absolute left-8 top-23" style="width: 38%" v-click>
  <img src="/ricky-kharawala-workshop-tools.jpg" alt="assorted hand tool lot on brown wooden shelf">

  <figcaption class="font-size-2">
  By <a href="https://unsplash.com/@sweetmangostudios?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Ricky  Kharawala</a> on <a href="https://unsplash.com/photos/assorted-hand-tool-lot-on-brown-wooden-shelf-4dVDBMAho8c?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  </figcaption>
</figure>

<figure class="absolute left-66 bottom-4" style="width: 44%" v-click>
  <img src="/s-w-workshop.jpg" alt="brown wooden workbench">

  <figcaption class="font-size-2">
  By <a href="https://unsplash.com/@wengenroad?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">s w</a> on <a href="https://unsplash.com/photos/brown-wooden-workbench-mNWsZDYUCFs?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  </figcaption>
</figure>

---

# Digital Workshop

<img
  src="/astro-logo.svg"
  alt="Astro"
  class="absolute top-[25%] left-[20%] h-20 rotate-[-8deg]"
/>

<img
  src="/storybook-logo.svg"
  alt="Storybook"
  class="absolute top-[18%] right-[22%] h-25 rotate-[6deg]"
/>

<img
  src="/vitepress-logo.svg"
  alt="Vitepress"
  class="absolute top-[34%] right-[48%] h-25 rotate-[2deg]"
/>

<img
  src="/ec-addon-docs-logo.png"
  alt="ember-cli-addon-docs"
  class="absolute bottom-[18%] left-[20%] h-15 rotate-[11deg]"
/>

<img
  src="/docfy-logo.svg"
  alt="Docfy"
  class="absolute right-[22%] bottom-[12%] h-15 rotate-[-12deg]"
/>


---
layout: full
---

<img src="/sb-hokulea-button-story.png" class="absolute top-10 bottom-10 left-1/2 max-w-full max-h-[calc(100%-5rem)] -translate-x-1/2 object-contain" alt="Storybook running Hokulea with the Button component" />

<div class="absolute top-10 h-4.5 w-115 left-1/2 ml-[-170px]" v-mark="{ at: ['+1', '+1'], color: 'red', type: 'box' }"></div>
<div class="absolute bottom-10 h-75 w-115 left-1/2 ml-[-170px]" v-mark="{ at: ['2', '+1'], color: 'red', type: 'box' }"></div>
<div class="absolute top-14 h-38 w-115 left-1/2 ml-[-170px]" v-mark="{ at: ['3', '+1'], color: 'green', type: 'box' }"></div>
<div class="absolute top-10 h-118 w-29 left-1/2 ml-[-290px]" v-mark="{ at: '4', color: 'blue', type: 'box' }"></div>

---

# Writing Stories

> A story captures the rendered state of a UI component.

```ts [button.stories.gts ~i-vscode-icons:file-type-storybook~]
import { Button } from './button.gts';
import type { Meta, StoryObj } from 'ember-storybook';

export default {
  title: 'Actions/Button',
  component: Button
} satisfies Meta;

export const Showcase: StoryObj = {};

export const WithIcon: StoryObj = {
  // ...
};

export const Stack: StoryObj = {
  // ...
};
```

---
layout: center
---

# Thank You

<div class="absolute left-10 bottom-10">
  <span>
    <p>Thomas Gossmann</p>
    <lucide-house /> <a href="https://gos.si" target="_blank">gos.si</a><br>
    <simple-icons-bluesky /> <a href="https://bsky.app/profile/gos.si" target="_blank">gos.si</a><br/>
    <simple-icons-github /> <a href="https://github.com/gossi" target="_blank">gossi</a><br>
  </span>
</div>

<div class="absolute bottom-10 right-10">
  <span>
    [WePlan Logo]
  </span>
</div>