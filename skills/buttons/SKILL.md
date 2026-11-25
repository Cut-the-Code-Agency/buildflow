---
name: buttons
description: Build, restyle or animate the button component on a Webflow site from a Figma design — one reusable button with variants, an icon or image you can switch per button, theme-aware colours and an optional hover animation. Use whenever the user mentions buttons, CTAs, call-to-action links, "the button component in the Styleguide", button variants or properties, arrow or icon buttons, switching icons on a button, a photo or avatar inside a button, lined/outlined/text buttons, or a hover effect on buttons — even if they do not say "skill". Also use when a build or componentize task reaches its first button. Requires a client repo (project.json); otherwise run the project skill first.
---

# buttons

The full instructions for this skill live on the Buildflow server. Before doing anything else, call the `buildflow_read` tool with path `skills/buttons/SKILL.md` and plugin `0.30.1`, and follow what it returns exactly, as if it were this file.

- Every `buildflow_read` call also passes `site` and `siteName`: `site.id` and `site.name` from `project.json` in the working folder, and `siteShortName` (`site.shortName`) when it is there. A Buildflow plan covers a set number of Webflow sites. Only while there is no `project.json` yet, leave them out. If the tool refuses because the site is not covered, tell the user that in plain words and stop; do not try another site id.

- Links written as `buildflow://<path>` point to further Buildflow files. Read them with `buildflow_read` (path without the `buildflow://` prefix, plugin `0.30.1`) whenever the instructions send you there.
- The loaded texts refer to this plugin's root as CLAUDE_PLUGIN_ROOT (a dollar sign and braces around that name). It is `${CLAUDE_PLUGIN_ROOT}`: scripts, the fixture, templates and hooks are there on disk. Pass this path on wherever the texts say to pass the plugin root.
- Read a file again with `buildflow_read` rather than reconstructing it from memory.
- The tool may carry a prefix (`mcp__…__buildflow_read`, from the Buildflow connector or MCP server); any tool named `buildflow_read` is the one. If a call with `plugin` fails, call it again without `plugin` (an app that connected before that argument existed rejects it).
- When `buildflow_read` is missing, asks for a login, or refuses, stop and run the `buildflow:start` skill, which walks the user through the setup. Do not improvise the workflow without it.
