---
name: start
description: Set up and check Buildflow step by step — the Buildflow login, the account, Webflow, Figma and this computer — then set up the folder for a site. Use when the user says "start buildflow", "buildflow instellen", "buildflow werkt niet", installs Buildflow for the first time, or when another Buildflow skill finds buildflow_read missing or asking for a login.
---

# Buildflow start

Walk the user through the setup. They are often marketers, not developers: plain words in their language, **one step at a time**, no jargon, no lists of options. After every instruction wait for "klaar" (or similar) and check again yourself before the next step. Tool names may carry a prefix (`mcp__<something>__`): match on the end of the name.

First find out where this runs: `echo $CLAUDE_CODE_ENTRYPOINT`. `cli` means a terminal; anything else is Claude Desktop. Use the matching instructions below and never give the other app's steps.

## 1. Buildflow

Call the tool ending in `buildflow_status` with plugin `0.29.0`. If that call fails, call it once more without `plugin` (an app that connected before that argument existed rejects it) before deciding anything.

- **No such tool, or it asks for a login**:
  - Claude Desktop: "Click **+** in the chat box, then **Connectors → Add connector → Add custom connector**. Name: **Buildflow**. URL: **https://buildflow.cutthecode.com/mcp**. Leave the rest as it is: Authentication **Sign in now** and OAuth client **Register automatically** (both marked *Detected*), Request headers and Advanced empty. Click **Add**, then **Connect**, and sign in with the account you use on buildflow.cutthecode.com. Then set **Read-only tools** to **Always allow**. Start a new session in the same folder and say *start buildflow* again." A new connector only reaches new sessions.
  - Terminal: run `claude mcp add --scope user --transport http buildflow https://buildflow.cutthecode.com/mcp --header "X-Buildflow-Plugin: 0.29.0"` yourself, then: "Type **/mcp**, choose **buildflow**, choose **Authenticate** and sign in." Check again after.
- **Account pending or revoked**: "Your account is not active yet. Cut the Code activates it; check https://buildflow.cutthecode.com/dashboard." Stop here.
- **Active**: one line ("Buildflow: <account>, active") and go on.

## 2. Webflow

Look for a tool ending in `data_sites_tool`.

- **Missing**:
  - Claude Desktop: "Click **+** in the chat box, then **Connectors → Add connector**, search **Webflow**, click **Connect** and sign in to Webflow. Start a new session and say *start buildflow* again."
  - Terminal: run `claude mcp add --scope user --transport http webflow https://mcp.webflow.com/mcp`, then: "Type **/mcp**, choose **webflow**, **Authenticate**."
- **Present**: list the sites the user can reach (one call), then call the `buildflow_status` tool again with plugin `0.29.0` and `webflow: true` (this ticks the Webflow step on the user's dashboard), and go on.

## 3. Figma (only for building from a Figma design)

Look for a tool whose name contains `figma` (for example ending in `get_design_context` or `get_metadata`). Present: call `buildflow_status` with plugin `0.29.0` and `figma: true` (ticks the Figma step on the dashboard). Missing: ask whether they want to rebuild designs from Figma; Webflow alone is enough for everything else. Yes → Claude Desktop: **+** in the chat box → Connectors → Add connector → **Figma** → Connect; terminal: `claude mcp add --scope user --transport http figma https://mcp.figma.com/mcp`, then /mcp → figma → Authenticate. No → skip.

## 4. This computer

Check quietly: `python3 --version`, `node --version`, and whether Google Chrome is installed (`/Applications/Google Chrome.app`).

- **python3** runs the safety check on Webflow changes. Missing, or macOS asks to install developer tools: "Click **Install** in the window that appears (it takes a few minutes), then say klaar." No window: "Download Python from https://www.python.org/downloads/, open the installer and click through it."
- **Node.js** and **Chrome** run the measuring scripts that compare the site with the design. Missing: "Download Node.js (LTS) from https://nodejs.org, open the installer and click through it." / "Install Google Chrome from https://www.google.com/chrome/." Building works without them, but checks against the design are weaker: say so once.

## 5. The folder for the site

Every site gets its own folder. The user never makes it: you do.

- Folder empty or new: run the `buildflow:project` skill here.
- Folder already holds a Buildflow project (`project.json`): say which site it is. If the user wants another site, go on as below; otherwise stop, the setup is done.
- Folder holds other things, or the user wants another site: ask which Webflow site (list them with the Webflow tools), make `~/Buildflow/<site-name>` (lowercase, dashes) and run the `buildflow:project` skill with that folder as the project folder: every path it writes is inside it. Then tell the user, once, where to work from now on. Claude Desktop: "Next time, choose the folder *Buildflow › <site-name>* with the folder button at the bottom of a new session." Terminal: `cd ~/Buildflow/<site-name> && claude`.

## 6. Done

Two lines: what is set up, and one example of what to ask now ("Bouw de hero uit deze Figma-link: …" or "Pas de knoppen op de homepage aan: …").
