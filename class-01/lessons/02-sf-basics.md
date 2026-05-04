# Lesson 02 — Salesforce Fundamentals

## What Is Salesforce?

A cloud-based CRM (Customer Relationship Management) platform. Companies use it to manage customers, sales pipelines, support cases, and internal processes. It runs entirely in the browser — no software to install, no servers to manage.

Salesforce is used across industries: manufacturing, healthcare, finance, retail, tech. SoundCraft Speakers uses it to manage their dealer network, track sales, and handle customer support.

## Core Concepts

| Concept | What It Is | Real Example |
|---------|-----------|--------------|
| **Org** | Your Salesforce instance — your company's environment | CTClass dev org |
| **Object** | A type of record, like a database table | Account, Contact, Opportunity |
| **Record** | One entry in an object | "SoundCraft Speakers" account |
| **Field** | A single piece of data on a record | Phone, Industry, Annual Revenue |
| **App** | A collection of tabs and tools grouped by function | Sales, Service, Marketing |
| **Tab** | A navigation item that points to an object or page | Accounts, Contacts, Reports |
| **View** | A filtered list of records within an object | "My Open Opportunities" |

## SoundCraft Speakers in Salesforce

SoundCraft sells to retail stores and distributors. In Salesforce:

- **Accounts** = the stores and distributors they sell to (e.g., AudioMax Retail)
- **Contacts** = the individual buyers at those stores (e.g., Jane Kim, Purchasing Manager)
- **Opportunities** = active deals (e.g., 500-unit order from AudioMax Retail, worth $449,500)
- **Cases** = support tickets (e.g., defective tweeter complaint from a customer)
- **Leads** = new potential buyers who haven't been qualified yet

## How Records Relate to Each Other

Records in Salesforce are connected. A Contact belongs to an Account. An Opportunity is tied to an Account and can have related Contacts. A Case links back to the Account and the Contact who filed it.

This means when a sales rep opens the AudioMax Retail account, they can see all the contacts there, every deal they've ever worked, and any open support tickets — all in one place. That's the core value of a CRM.

## Standard vs. Custom

Salesforce ships with standard objects like Account, Contact, Lead, Opportunity, and Case. You can also build **custom objects** for anything that doesn't fit out of the box.

For SoundCraft, a custom object might look like:
- `Speaker_Model__c` — tracks product catalog (model name, wattage, MSRP)
- `Dealer_Agreement__c` — tracks contracts with retail partners

The `__c` suffix means custom — you'll see it on any field or object that wasn't part of the original Salesforce package.

## The Salesforce Data Model

Think of it like a spreadsheet — but relational:

```
Account (AudioMax Retail)
  └── Contact (Jane Kim)
  └── Opportunity (500-unit order — $449,500)
  └── Case (Defective tweeter — open)
```

Every piece of information traces back to the Account. This is called the **account-centric model** and it's how most Salesforce implementations are structured.

## Navigating the UI

- **App Launcher** (9-dot grid, top left) — switch between apps
- **Search bar** — find any record across the org instantly
- **Recent Items** — quick access to records you've viewed
- **Setup** (gear icon, top right) — admin and configuration area — this is where you build custom objects, fields, and page layouts
