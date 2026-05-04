# Lesson 04 — Tools

## Salesforce Inspector Reloaded

A free Chrome/Edge extension that lets you inspect and query your Salesforce org directly from the browser.

**Install:** [Salesforce Inspector Reloaded — Chrome Web Store](https://chromewebstore.google.com/detail/salesforce-inspector-relo/hpijlohoihegkfehhibggnkbjhoemldh?hl=en&pli=1)

### What You Can Do

- **View field API names** — hover over any field on a record to see its internal name (e.g., `Annual_Revenue__c`)
- **Run SOQL queries** — query your org's data like a database
- **Export/import records** — great for loading test data
- **Inspect page metadata** — see what's on the page behind the scenes

### Quick SOQL Example

```sql
SELECT Id, Name, Industry, AnnualRevenue
FROM Account
WHERE Industry = 'Electronics'
ORDER BY AnnualRevenue DESC
LIMIT 10
```

## VS Code Org Browser

Built into the Salesforce Extension Pack. Lets you explore your org's metadata directly in VS Code without touching the CLI.

**How to open:** Click the Salesforce cloud icon in the VS Code left sidebar → Org Browser

### What You Can Do

- **Browse metadata** — expand any type (Objects, LWC, Apex, etc.) to see what's in your org
- **Retrieve to project** — right-click any item and choose **Retrieve This Source** to pull it into your local project
- **No CLI required** — everything is point and click

Set your default org first so the Org Browser knows what to connect to:
```bash
sf config set target-org myOrg
```

## Claude Code

An AI coding assistant built into VS Code. Use it to:
- Explain unfamiliar Salesforce concepts
- Debug Apex or JavaScript errors
- Write SOQL queries

**Remember:** Claude Code shows you every command before running it. Read first, approve second.

## Salesforce CLI (`sf`)

The command-line tool for everything Salesforce: deploying code, pulling org changes, importing data, running tests.

Key commands to know:
```bash
sf org open --target-org myOrg               # open org in browser
sf project deploy start --target-org myOrg   # push code to org
sf project retrieve start --target-org myOrg # pull changes from org
```
