# Lesson 02 — Salesforce Fundamentals

## What Is Salesforce?

A cloud-based CRM (Customer Relationship Management) platform. Companies use it to manage customers, sales pipelines, support cases, and internal processes.

## Core Concepts

| Concept | What It Is | Real Example |
|---------|-----------|--------------|
| **Org** | Your Salesforce instance | CTClass dev org |
| **Object** | A type of record (like a database table) | Account, Contact, Opportunity |
| **Record** | One entry in an object | "SoundCraft Speakers" account |
| **Field** | A piece of data on a record | Phone, Industry, Revenue |
| **App** | A collection of tabs and functionality | Sales, Service, Marketing |

## SoundCraft Speakers in Salesforce

SoundCraft sells to retail stores and distributors. In Salesforce:

- **Accounts** = the stores and distributors they sell to
- **Contacts** = the buyers at those stores
- **Opportunities** = active deals (e.g., 500-unit order from AudioMax Retail)
- **Cases** = support tickets (e.g., defective tweeter complaint)

## Standard vs. Custom

Salesforce ships with standard objects (Account, Contact, Lead, Opportunity). You can also build **custom objects** — for example, SoundCraft might have a `Speaker_Model__c` object to track their product catalog.
