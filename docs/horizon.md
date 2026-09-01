---
icon: lucide/folder-code
---

# Horizon Migration

This document outlines the migration from our current Shopify theme (based on Dawn) to the new blocks-based Horizon architecture.

## Context

In 2025, Shopify announced the release of Horizon, a new theme block based architecture that replaces the traditional section-based template system. This architecture provides a more flexible and maintainable way to build and customize Shopify themes.

**Further, in July 2026, Shopify announced that a new major release of Horizon would be avaiable in August or September 2026.** This new release will once again change the way we approach theme development, with the following key changes:

* Liquid-first composition model
* Improvements to the Liquid rendering engine, including support for `{% partial %}` and `{% block %}`
* Tailwind support

These changes will significantly impact the way we write our theme code, and will require a comprehensive migration plan.

??? info "Recommendation"

    **My recommendation** is to wait until the new major release of Horizon is available, and then use that release as a foundation to migrate to the new architecture. We should keep an eye on the Shopify blog and documentation for updates on this release.

In the meantime, we should familiarize ourselves with the new architecture and start planning how we will migrate our existing codebase. This will align with Phase 0 and 0.5 of our migration plan.

[Source: Shopify Community Developer Forums](https://community.shopify.dev/t/liquid-templates-with-block-render-is-a-flexibility-regression/36236)
>The promise we make with Liquid themes is that everything is a forever API — so JSON templates will always be supported.
Similarly, 15 years of themes using Liquid templates, pre-JSON, are still supported.
What we’re previewing now is the architecture we believe in for the future, and that we’re investing the most into — but there are a number of things that still need to come before this gets to parity with JSON templates. Editor support as a whole is the first thing we’re working on. We will also later have support for Apps, Markets contextualization, and Rollouts. These are all mission-critical things to land before we encourage widespread adoption of this architecture.
Our goal with this preview is to give all our developers as much heads up as possible so they can start to think about how they want to work, and so they can give us feedback on what feels good and what still needs some love.
If building a theme today, the best advice I could give to be aligned with how we’re thinking about the future is —
Build with Theme Blocks as the core composition layer
Use Tailwind for styling
Don’t try to make every single thing a setting, constrain yourself to just the things you would need in a polished, tight design system — usually under 5 settings per block. 2-3 in many cases. (Text and media settings excluded from that count).
Partials + Standard Actions for all mutations and reactivity
Then you get very little difference between the templates and converting it to Liquid in the future, if you want, becomes trivial.

!!! note

    Shopify has provided a development preview of the new Horizon theme `base-theme-next` 
    As it's still in developement, we should not rely on it for production use.

## Migration Steps

### Phase 0: Planning and Current-State Inventory
* [ ]  Conduct a comprehensive audit of the current theme codebase
* [ ]  Remove any unused or deprecated sections, blocks, and components
* [ ]  Document all custom sections and blocks that will need to be migrated
* [ ]  Identify dependencies and integrations with third-party apps
* [ ]  Create a detailed migration plan with timelines and responsibilities

### Phase 0.5: Conventions and Workflow
* [ ]  Establish coding conventions for the new architecture
* [ ]  Set up CI/CD pipelines for Theme Check, linting, and formatting
* [ ]  AGENTS.MD for agent-assisted development
* [ ]  Standardizing commit messages (conventional, scoped) and PR templates
* [ ]  Setting up a shared documentation system for the team, including changelog management
* [ ]  Integrating design system documentation into the workflow