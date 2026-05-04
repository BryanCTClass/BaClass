# Lesson 04 — Tools

## Salesforce Inspector Reloaded

A free Chrome/Edge extension that lets you inspect and query your Salesforce org directly from the browser.

**Install:** Chrome Web Store → search "Salesforce Inspector Reloaded"

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

## Claude Code

An AI coding assistant built into VS Code. Use it to:
- Generate boilerplate LWC files
- Explain unfamiliar Salesforce concepts
- Debug Apex or JavaScript errors
- Write SOQL queries

**Remember:** Claude Code shows you every command before running it. Read first, approve second.

## Salesforce CLI (`sf`)

The command-line tool for everything Salesforce: deploying code, pulling org changes, importing data, running tests.

Key commands to know:
```bash
sf org open --target-org CTClass               # open org in browser
sf project deploy start --target-org CTClass   # push code to org
sf project retrieve start --target-org CTClass # pull changes from org
```
