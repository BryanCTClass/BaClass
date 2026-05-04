# Setup Guide — Mac

Follow every step in order. Each step has a verification so you know it worked before moving on.

---

## Step 1 — Sign Up for a Salesforce Developer Org

1. Go to [https://developer.salesforce.com/signup](https://developer.salesforce.com/signup)
2. Fill out the form. Use a real email address — you'll need to verify it.
3. Check your email and click the verification link.
4. Set your password when prompted.
5. You should land on a Salesforce screen that says **"Welcome to Salesforce"** or your org's home page.

**Keep your login URL handy.** It looks like:
```
https://something.my.salesforce.com
```

---

## Step 2 — Install VS Code

1. Go to [https://code.visualstudio.com](https://code.visualstudio.com)
2. Click **Download for Mac**
3. Open the downloaded `.zip` file — it will extract **Visual Studio Code.app**
4. Drag **Visual Studio Code.app** into your **Applications** folder
5. Open VS Code from Applications

**Verify:** VS Code opens and you see a welcome screen.

---

## Step 3 — Install the Salesforce Extension Pack

1. In VS Code, click the **Extensions** icon in the left sidebar (it looks like four squares)
2. In the search bar, type: `Salesforce Extension Pack`
3. Click the result published by **Salesforce**
4. Click **Install**
5. Wait for it to finish — it installs several extensions at once

**Verify:** In the left sidebar, you should now see a cloud icon labeled **Salesforce**.

---

## Step 4 — Install Claude Code

1. In VS Code, click the **Extensions** icon again
2. Search for: `Claude Code`
3. Click the result published by **Anthropic**
4. Click **Install**

**Verify:** A Claude icon appears in the left sidebar or bottom status bar of VS Code.

---

## Step 5 — Install Node.js

Node.js is required by the Salesforce CLI. First check if you already have it.

Open **Terminal** (search for it in Spotlight with `Cmd + Space`), then run:

```bash
node --version
```

- If you see a version number like `v18.0.0` or higher — **skip to Step 6.**
- If you see `command not found` — continue below.

**To install Node.js:**
1. Go to [https://nodejs.org](https://nodejs.org)
2. Click the **LTS** download button
3. Open the downloaded `.pkg` file and follow the installer

**Verify:**
```bash
node --version
```
You should see a version number.

---

## Step 6 — Install the Salesforce CLI

In Terminal, run:

```bash
npm install -g @salesforce/cli
```

This may take a minute or two.

**Verify:**
```bash
sf --version
```
You should see something like `@salesforce/cli/2.x.x`.

---

## Step 7 — Check Python

Python is used in some class scripts for processing data.

```bash
python3 --version
```

- If you see `Python 3.x.x` — **skip to Step 8.**
- If you see `command not found`:
  1. Go to [https://www.python.org/downloads](https://www.python.org/downloads)
  2. Click **Download Python 3.x.x**
  3. Open the `.pkg` installer and follow the steps

**Verify:**
```bash
python3 --version
```
You should see a version number starting with `3`.

---

## Step 8 — Install Git

Check if Git is already installed:

```bash
git --version
```

- If you see a version number — **skip to Step 8.**
- If a popup appears asking you to install **Xcode Command Line Tools** — click **Install** and wait for it to finish.

**Verify:**
```bash
git --version
```
You should see a version number.

---

## Step 9 — Connect to Your Salesforce Org

Run this command in Terminal, replacing the URL with your own org's login URL:

```bash
sf org login web --instance-url https://YOUR-ORG-URL.my.salesforce.com --alias myOrg
```

A browser window will open. Log in with your Salesforce credentials. When you see a page that says **"You may close this window"**, close it and return to Terminal.

**Verify:**
```bash
sf org display --target-org myOrg
```
You should see a table with your username and **Connected Status: Connected**.

---

## Step 10 — Open the Org in the Browser

```bash
sf org open --target-org myOrg
```

This should open your Salesforce org in the browser directly from Terminal.

---

## Step 11 — Set Up the VS Code Org Browser

The Org Browser is built into the Salesforce Extension Pack and lets you explore your org's metadata directly inside VS Code — without touching the CLI.

1. Open VS Code and make sure your class project folder is open (**File → Open Folder**)
2. In Terminal, set your org as the default for this project:
```bash
sf config set target-org myOrg
```
3. Click the **Salesforce cloud icon** in the left sidebar
4. You should see an **Org Browser** panel listing metadata types (Objects, Apex Classes, LWC, etc.)
5. Click any type to expand it and browse what's in your org
6. Right-click any item and choose **Retrieve This Source** to pull it into your project

**Verify:** You can see metadata types listed under Org Browser in the sidebar.

---

## You're Done

Everything is installed and connected. Let your instructor know you've completed setup.
