---
name: navigation
description: Build, restyle or animate the site navigation on a Webflow site from a Figma design — the nav bar, its page links, a menu/burger button, a full-screen or drop-down menu panel, a logo that shrinks on scroll, links that hide on scroll, and a nav that changes colour over dark sections. Use whenever the user mentions the nav, navbar, navigation, header, menu, burger/hamburger, "Menu / Close", the menu overlay or panel, nav links, the logo in the nav, a sticky or shrinking header, nav colour per section, or a language switch in the nav — even if they do not say "skill". Requires a client repo (project.json); otherwise run the project skill first.
---

# navigation

The full instructions for this skill live on the Buildflow server. Before doing anything else, call the `buildflow_read` tool with path `skills/navigation/SKILL.md` and plugin `0.28.0`, and follow what it returns exactly, as if it were this file.

- Every `buildflow_read` call also passes `site` and `siteName`: `site.id` and `site.name` from `project.json` in the working folder. A Buildflow licence covers one Webflow site. Only while there is no `project.json` yet, leave them out. If the tool refuses because the site is not covered, tell the user that in plain words and stop; do not try another site id.

- Links written as `buildflow://<path>` point to further Buildflow files. Read them with `buildflow_read` (path without the `buildflow://` prefix, plugin `0.28.0`) whenever the instructions send you there.
- The loaded texts refer to this plugin's root as CLAUDE_PLUGIN_ROOT (a dollar sign and braces around that name). It is `${CLAUDE_PLUGIN_ROOT}`: scripts, the fixture, templates and hooks are there on disk. Pass this path on wherever the texts say to pass the plugin root.
- Read a file again with `buildflow_read` rather than reconstructing it from memory.
- The tool may carry a prefix (`mcp__…__buildflow_read`, from the Buildflow connector or MCP server); any tool named `buildflow_read` is the one. If a call with `plugin` fails, call it again without `plugin` (an app that connected before that argument existed rejects it).
- When `buildflow_read` is missing, asks for a login, or refuses, stop and run the `buildflow:start` skill, which walks the user through the setup. Do not improvise the workflow without it.
