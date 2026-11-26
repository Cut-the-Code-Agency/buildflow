---
name: accessibility
description: Make and check a Webflow site accessible to WCAG 2.2 AA — keyboard use and visible focus, focus order, menus and modals that open, close and hand focus back, skip link, landmarks, headings, lists, alt text and decorative elements, accessible names on icon buttons, contrast per theme and per brand, zoom, reflow and text spacing, target size, motion with a pause, forms and embedded iframes, status messages, captions and transcripts — and verify it on the published site with axe-core plus a keyboard walk. Use when the user mentions accessibility, toegankelijkheid, a11y, WCAG, screen readers, keyboard navigation, focus states, contrast, alt texts, aria, "skip to main", an accessibility checklist or audit; before showing a site to the client; before launch; and whenever a nav, menu, modal, slider, tabs, accordion, form or card grid is built. Requires a client repo (project.json); otherwise run the project skill first.
---

# accessibility

The full instructions for this skill live on the Buildflow server. Before doing anything else, call the `buildflow_read` tool with path `skills/accessibility/SKILL.md` and plugin `0.33.0`, and follow what it returns exactly, as if it were this file.

- Every `buildflow_read` call also passes `site` and `siteName`: `site.id` and `site.name` from `project.json` in the working folder, and `siteShortName` (`site.shortName`) when it is there. A Buildflow plan covers a set number of Webflow sites. Only while there is no `project.json` yet, leave them out. If the tool refuses because the site is not covered, tell the user that in plain words and stop; do not try another site id.

- Links written as `buildflow://<path>` point to further Buildflow files. Read them with `buildflow_read` (path without the `buildflow://` prefix, plugin `0.33.0`) whenever the instructions send you there.
- The loaded texts refer to this plugin's root as CLAUDE_PLUGIN_ROOT (a dollar sign and braces around that name). It is `${CLAUDE_PLUGIN_ROOT}`: scripts, the fixture, templates and hooks are there on disk. Pass this path on wherever the texts say to pass the plugin root.
- Read a file again with `buildflow_read` rather than reconstructing it from memory.
- The tool may carry a prefix (`mcp__…__buildflow_read`, from the Buildflow connector or MCP server); any tool named `buildflow_read` is the one. If a call with `plugin` fails, call it again without `plugin` (an app that connected before that argument existed rejects it).
- When `buildflow_read` is missing, asks for a login, or refuses, stop and run the `buildflow:start` skill, which walks the user through the setup. Do not improvise the workflow without it.
