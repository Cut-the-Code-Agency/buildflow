---
name: seo
description: Set up and check the SEO of a Webflow site — page titles, meta descriptions and Open Graph share images on every static page and CMS template, SEO fields per CMS collection with one share image per item, every locale, noindex on internal pages — and finish with a full SEO audit of the published site: landmark order, one h1 and no skipped headings, no headings in overview cards, robots.txt pagination rules, canonical and Open Graph tags, alt texts and video captions, descriptive and crawlable links, lazy loading and the hero image, fonts, layout shift, and schema.org structured data (Article, FAQPage, Organization, BreadcrumbList, JobPosting). Use when a page or CMS collection is added, when the user asks about SEO, meta titles or descriptions, share images, Open Graph, "what shows on LinkedIn/WhatsApp", noindex, sitemap, robots.txt, headings, alt texts, structured data or schema, Core Web Vitals, an SEO check or audit, before showing a site to the client, and before launch. Requires a client repo (project.json); otherwise run the project skill first.
---

# seo

The full instructions for this skill live on the Buildflow server. Before doing anything else, call the `buildflow_read` tool with path `skills/seo/SKILL.md` and plugin `0.29.0`, and follow what it returns exactly, as if it were this file.

- Every `buildflow_read` call also passes `site` and `siteName`: `site.id` and `site.name` from `project.json` in the working folder, and `siteShortName` (`site.shortName`) when it is there. A Buildflow plan covers a set number of Webflow sites. Only while there is no `project.json` yet, leave them out. If the tool refuses because the site is not covered, tell the user that in plain words and stop; do not try another site id.

- Links written as `buildflow://<path>` point to further Buildflow files. Read them with `buildflow_read` (path without the `buildflow://` prefix, plugin `0.29.0`) whenever the instructions send you there.
- The loaded texts refer to this plugin's root as CLAUDE_PLUGIN_ROOT (a dollar sign and braces around that name). It is `${CLAUDE_PLUGIN_ROOT}`: scripts, the fixture, templates and hooks are there on disk. Pass this path on wherever the texts say to pass the plugin root.
- Read a file again with `buildflow_read` rather than reconstructing it from memory.
- The tool may carry a prefix (`mcp__…__buildflow_read`, from the Buildflow connector or MCP server); any tool named `buildflow_read` is the one. If a call with `plugin` fails, call it again without `plugin` (an app that connected before that argument existed rejects it).
- When `buildflow_read` is missing, asks for a login, or refuses, stop and run the `buildflow:start` skill, which walks the user through the setup. Do not improvise the workflow without it.
