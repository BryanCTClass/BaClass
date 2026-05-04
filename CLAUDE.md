# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This workspace is used for an intro Salesforce and Business Analysis class. It connects to a Salesforce Developer org for hands-on exploration and development.

## Salesforce CLI Setup

This project uses the Salesforce CLI (`sf`) to interact with a connected Developer org.

```bash
# Authenticate with a Developer org (opens browser)
sf org login web --instance-url https://orgfarm-cfc91dec69-dev-ed.develop.my.salesforce.com --alias CTClass

# Verify connected org
sf org display --target-org CTClass

# Open the org in a browser
sf org open --target-org CTClass

# Deploy a specific component
sf project deploy start --source-dir force-app/main/default/lwc/myComponent --target-org CTClass

# Deploy all metadata
sf project deploy start --target-org CTClass

# Pull changes from the org
sf project retrieve start --target-org CTClass

# Import mock data (using a data plan)
sf data import tree --plan data/data-plan.json --target-org CTClass
```

## Project Structure (when scaffolded)

```
force-app/main/default/
  lwc/          # Lightning Web Components
  objects/      # Custom objects and fields
  data/         # Mock data files (JSON) and data plans
sfdx-project.json  # Salesforce project config
```

## Scaffold a New Project

If starting fresh:
```bash
sf project generate --name class-project --template standard
cd class-project
```

## LWC Basics

Each LWC lives in its own folder under `lwc/` and requires three files:
- `componentName.html` — template
- `componentName.js` — controller
- `componentName.js-meta.xml` — metadata (targets, API version)

## Safety Notes

- Always review the full command before running it — Claude Code will show you what it plans to execute
- Do not deploy to a production org from this workspace; use the connected Developer org only
- If prompted to run an unfamiliar command, ask what it does before approving
