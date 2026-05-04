# Setup Guide — Windows

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
2. Click **Download for Windows**
3. Open the downloaded `.exe` file
4. Accept the license agreement
5. On the **Select Additional Tasks** screen, check **all boxes** — especially:
   - Add to PATH
   - Register Code as an editor for supported file types
6. Click **Install**, then **Finish**

**Verify:** Open VS Code from the Start menu. You should see a welcome screen.

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

Open **Command Prompt** (press `Windows + R`, type `cmd`, press Enter), then run:

```
node --version
```

- If you see a version number like `v18.0.0` or higher — **skip to Step 6.**
- If you see `'node' is not recognized` — continue below.

**To install Node.js:**
1. Go to [https://nodejs.org](https://nodejs.org)
2. Click the **LTS** download button
3. Open the downloaded `.msi` file and follow the installer
4. **Important:** When asked about **"Tools for Native Modules"**, you can leave this unchecked
5. Restart Command Prompt after installation

**Verify:**
```
node --version
```
You should see a version number.

---

## Step 6 — Install the Salesforce CLI

In Command Prompt, run:

```
npm install -g @salesforce/cli
```

This may take a minute or two.

**Verify:**
```
sf --version
```
You should see something like `@salesforce/cli/2.x.x`.

If you see `'sf' is not recognized`, close and reopen Command Prompt and try again.

---

## Step 7 — Install Git

1. Go to [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. The download should start automatically — open the `.exe` installer
3. Click through the installer using the **default settings on every screen**
   - Do not change any defaults — they are set correctly for most users
4. Finish the installer

**Verify:** Open a new Command Prompt window and run:
```
git --version
```
You should see a version number. If not, restart your computer and try again.

---

## Step 8 — Connect to Your Salesforce Org

Open Command Prompt and run the following, replacing the URL with your own org's login URL:

```
sf org login web --instance-url https://YOUR-ORG-URL.my.salesforce.com --alias myOrg
```

A browser window will open. Log in with your Salesforce credentials. When you see a page that says **"You may close this window"**, close it and return to Command Prompt.

**Verify:**
```
sf org display --target-org myOrg
```
You should see a table with your username and **Connected Status: Connected**.

---

## Step 9 — Open the Org in the Browser

```
sf org open --target-org myOrg
```

This should open your Salesforce org in the browser directly from Command Prompt.

---

## Step 10 — Set Up the VS Code Org Browser

The Org Browser is built into the Salesforce Extension Pack and lets you explore your org's metadata directly inside VS Code — without touching the CLI.

1. Open VS Code and make sure your class project folder is open (**File → Open Folder**)
2. In the VS Code terminal, set your org as the default for this project:
```
sf config set target-org myOrg
```
3. Click the **Salesforce cloud icon** in the left sidebar
4. You should see an **Org Browser** panel listing metadata types (Objects, Apex Classes, LWC, etc.)
5. Click any type to expand it and browse what's in your org
6. Right-click any item and choose **Retrieve This Source** to pull it into your project

**Verify:** You can see metadata types listed under Org Browser in the sidebar.

---

## Common Problems on Windows

**"sf is not recognized" after installing:**
Close Command Prompt completely and reopen it. If it still fails, restart your computer.

**Browser doesn't open during org login:**
Copy the URL that appears in Command Prompt and paste it manually into your browser.

**Node installed but npm commands fail:**
Search for **"Environment Variables"** in the Start menu → click **"Edit the system environment variables"** → click **"Environment Variables"** → check that `C:\Users\YourName\AppData\Roaming\npm` appears in your **Path** variable. If not, add it.

---

## You're Done

Everything is installed and connected. Let your instructor know you've completed setup.
