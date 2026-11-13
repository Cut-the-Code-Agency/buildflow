---
name: feedback
description: Work through the client's feedback tickets in ClickUp until the "new" column is empty — check that ClickUp is logged in as the user, find the project's Feedback list, read every new ticket with its screenshot, fix it on the Webflow site with fixer agents, publish, have fresh reviewers check it live, and set each ticket that passes to "in review" with a comment. Use whenever the user says "work on the feedback", "do the ClickUp tickets", "empty the new column", "the Feedback board", "Marker.io tickets", "there are new tickets", or pastes a ClickUp board link with feedback. Requires a client repo (project.json); otherwise run the project skill first.
---

# feedback

The full instructions for this skill live on the Buildflow server. Before doing anything else, call the `buildflow_read` tool with path `skills/feedback/SKILL.md` and plugin `0.28.0`, and follow what it returns exactly, as if it were this file.

- Links written as `buildflow://<path>` point to further Buildflow files. Read them with `buildflow_read` (path without the `buildflow://` prefix, plugin `0.28.0`) whenever the instructions send you there.
- The loaded texts refer to this plugin's root as CLAUDE_PLUGIN_ROOT (a dollar sign and braces around that name). It is `${CLAUDE_PLUGIN_ROOT}`: scripts, the fixture, templates and hooks are there on disk. Pass this path on wherever the texts say to pass the plugin root.
- Read a file again with `buildflow_read` rather than reconstructing it from memory.
- The tool may carry a prefix (`mcp__…__buildflow_read`, from the Buildflow connector or MCP server); any tool named `buildflow_read` is the one.
- When `buildflow_read` is missing, asks for a login, or refuses, stop and run the `buildflow:start` skill, which walks the user through the setup. Do not improvise the workflow without it.
