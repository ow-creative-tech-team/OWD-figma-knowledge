# OWD Figma Copilot

OWD Figma Copilot is a chat-based assistant for working directly inside Figma. It lets you describe design tasks in natural language, then helps inspect the canvas, understand selected layers, apply edits, organize files, create reusable design-system structures, and automate repetitive Figma work.

Powered by GPT5-mini (MMC).

## Core Concept

Instead of asking you to manually script every change, Figma Copilot works like a design-aware agent. You can ask it to look at the current selection, review the page structure, read local styles or variables, create or update layers, and run Figma Plugin API actions on your behalf.

The assistant can move between conversation and action:

- inspect the selected frame, component, page, styles, variables, or local components
- explain what it finds before making changes
- generate and run Figma actions to edit the canvas
- create components, variants, auto-layout structures, naming systems, and export workflows
- use reusable skills for specialized workflows
- report what it changed after each task

You can use it for small one-off edits or larger guided workflows, such as preparing a design system, cleaning up a file, exporting assets, or reviewing a screen for accessibility.

## What You Can Ask It To Do

Figma Copilot is useful for design operations that are repetitive, structured, or easier to describe than perform manually.

Common possibilities include:

- **Canvas inspection**: summarize the current selection, list page structure, find components, review styles, or inspect variables.
- **Layer cleanup**: rename layers, group related objects, normalize frame names, remove messy placeholder naming, or organize sections.
- **Component work**: create buttons, cards, form fields, component sets, variants, and reusable auto-layout structures.
- **Design-system support**: create variables, review token names, map colors to styles, document component usage, or check consistency.
- **Accessibility review**: check readability, contrast, focus order, label clarity, and hierarchy.
- **Export preparation**: prepare icons, assets, favicons, or selected nodes for cleaner export.
- **Bulk edits**: apply spacing, padding, corner radius, typography, fills, or naming rules across many layers.
- **File understanding**: ask what is on the page, what components exist, how a selected structure is built, or where inconsistencies appear.

## Skills

Skills are reusable instructions that teach the assistant how to handle a specific workflow. A skill can define naming rules, design-system conventions, accessibility checks, export rules, brand guidance, or any repeated task you want the assistant to perform consistently.

Figma Copilot supports both built-in passive skills and user-created skills.

### Built-In Passive Skills

Built-in passive skills are ready-made workflows included with the plugin. They are passive, which means they do not have to affect every request. The assistant can call on them when they are relevant, and you can explicitly call them with an `@skill-name` mention.

Examples:

- `@accessibility Review the selected frame for readability and contrast.`
- `@design-tokens Create variables from the selected color styles.`
- `@component-builder Turn this card into a production-ready component.`
- `@icon-exporter Prepare these icons for export.`

### User-Created Skills

You can also create your own reusable skills for personal, team, brand, or project-specific workflows. User-created skills can be called the same way as built-in skills, using `@skill-name`.

Examples:

- `@brand-review Check this landing page against our brand rules.`
- `@file-cleanup Rename and organize the selected layers.`
- `@mobile-ui-audit Review this screen for mobile usability issues.`

This makes skills useful for repeatable standards such as:

- brand voice and visual rules
- component naming conventions
- spacing and layout rules
- export requirements
- accessibility review steps
- design handoff checks

## Creating A Reusable Skill

When you want the assistant to remember a repeatable workflow, ask it to create a skill. The assistant can use the `create_skill` tool to save a reusable skill document for that task.

Short instructions:

1. Tell Figma Copilot what the skill should be called.
2. Describe when the skill should be used.
3. List the rules, checks, or steps the assistant should follow.
4. Ask for it to be saved as a passive skill if you want to call it only when needed.
5. Use it later with `@skill-name`.

Example prompt:

```text
Create a passive skill called product-card-audit.
Use it when I ask the assistant to review ecommerce product cards.
It should check image sizing, price visibility, CTA clarity, spacing, accessibility, and whether the card works in a responsive grid.
```

Example user-created skill:

```md
# product-card-audit

Use when reviewing ecommerce product cards.

Rules:
- Check that the product image is clear and consistently framed.
- Make sure the product name, price, and CTA are easy to scan.
- Verify spacing between image, title, price, metadata, and button.
- Flag weak contrast, small text, or unclear interaction states.
- Suggest improvements without changing the design unless asked.
```

Later, you can call it like this:

```text
@product-card-audit Review the selected product cards and tell me what should be improved.
```

## Example Prompts

Try prompts like:

- `What is selected right now?`
- `Summarize the structure of this page.`
- `Review the selected frame for visual hierarchy and spacing issues.`
- `Create a reusable button component from this selected frame.`
- `Turn these three cards into a component set with variants.`
- `Rename all selected layers using clean, file-safe names.`
- `Create color variables from the local paint styles.`
- `Find inconsistent spacing in this selected section.`
- `@accessibility Check this screen for contrast and readability problems.`
- `@component-builder Convert this input field into a production-ready component.`
- `@design-tokens Create semantic variables for these colors.`
- `Prepare all selected icons for export as SVG.`
- `Create a passive skill for our team's modal dialog rules.`
- `Use my @brand-review skill and audit this landing page.`

## Practical Tips

- Start with the current selection when you want precise changes.
- Ask the assistant to inspect first if you want a review before edits.
- Use `@skill-name` when you want a specific workflow or standard applied.
- Create skills for anything you expect to repeat more than once.
- Be explicit about whether you want analysis only or actual canvas changes.
- For broad page-wide changes, ask for a short plan before applying edits.

## Good Use Cases

Figma Copilot is especially helpful for:

- design-system maintenance
- component cleanup
- accessibility review
- repetitive layout edits
- naming and organization
- token and variable work
- export preparation
- design QA before handoff
- creating custom reusable workflows through skills
