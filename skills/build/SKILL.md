---
name: build
description: Build or change something on a Webflow site and verify it against its source. Use when the user gives a Figma URL or frame to build, asks to change, fix or restyle something on the site (often with a screenshot), asks to put final copy from a document onto a page, or asks for a new section or page "in the style of the site" with no design, or asks to prepare a site for a Figma design (fill in Lumos, variables, themes, fonts, type scale). Requires a client repo (project.json in the cwd); otherwise run the project skill first.
---

# build

The full instructions for this skill live on the Buildflow server. Before doing anything else, call the `buildflow_read` tool with path `skills/build/SKILL.md` and follow what it returns exactly, as if it were this file.

- Links written as `buildflow://<path>` point to further Buildflow files. Read them with `buildflow_read` (path without the `buildflow://` prefix) whenever the instructions send you there.
- The loaded texts refer to this plugin's root as CLAUDE_PLUGIN_ROOT (a dollar sign and braces around that name). It is `${CLAUDE_PLUGIN_ROOT}`: scripts, the fixture, templates and hooks are there on disk. Pass this path on wherever the texts say to pass the plugin root.
- Read a file again with `buildflow_read` rather than reconstructing it from memory.
- When `buildflow_read` is missing, asks for a login, or refuses, stop and tell the user what it said (setup and account: https://buildflow.cutthecode.com). Do not improvise the workflow without it.
