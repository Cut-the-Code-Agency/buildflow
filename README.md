# Buildflow by Cut The Code (client plugin)

Version 0.28.0. Build and change Webflow sites with Claude Code, the way Cut The Code does.

This plugin carries what runs on your machine: hooks, the builder agent, scripts, the measuring fixture and the project templates. The instructions themselves are loaded from Buildflow server while you work, so you need an active account.

## Install

Sign in at https://buildflow.cutthecode.com, then:

```
curl -fsSL https://buildflow.cutthecode.com/install | sh
```

or by hand:

```
claude plugin marketplace add Cut-the-Code-Agency/buildflow
claude plugin install buildflow@cutthecode
```

Connect the Webflow and Figma MCP servers yourself (the portal shows the commands), then run `/buildflow:project` in an empty folder for each site.

How it works, what is stored where, and how updates reach you: https://buildflow.cutthecode.com/hoe-het-werkt

Use of Buildflow is subject to the terms you accepted in the portal.
