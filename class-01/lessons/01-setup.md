# Lesson 01 — Setup

## What You Need

1. **VS Code** — [code.visualstudio.com](https://code.visualstudio.com)
2. **Claude Code** — install via VS Code extension marketplace, search "Claude Code"
3. **Salesforce CLI** — [developer.salesforce.com/tools/salesforcecli](https://developer.salesforce.com/tools/salesforcecli)
4. **Salesforce Extension Pack** — VS Code marketplace, search "Salesforce Extension Pack"

## Connect to the Dev Org

```bash
sf org login web \
  --instance-url https://orgfarm-cfc91dec69-dev-ed.develop.my.salesforce.com \
  --alias CTClass
```

This opens a browser. Log in with your org credentials. When you see "Connected," close the tab and return to VS Code.

Verify it worked:
```bash
sf org display --target-org CTClass
```

## Safety

Claude Code shows you every command it wants to run before executing it. **Always read it before approving.**

Rules to follow:
- If you don't understand a command, ask — don't approve it
- Never run `rm`, `drop`, or `delete` commands without understanding the scope
- Never deploy to a production org from this workspace
