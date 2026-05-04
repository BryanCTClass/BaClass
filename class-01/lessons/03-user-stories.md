# Lesson 03 — User Stories

## What Is a User Story?

A short, plain-language description of a feature from the perspective of the person who needs it.

**Format:**
> As a **[role]**, I want to **[action]**, so that **[benefit]**.

## Why They Matter

User stories keep development focused on real needs instead of technical assumptions. As a BA, writing good user stories is one of your core deliverables.

## SoundCraft Examples

**Sales:**
> As a **sales rep**, I want to see all open opportunities for an account on one screen, so that I can prepare for my next call without switching tabs.

**Operations:**
> As a **warehouse manager**, I want to receive an alert when inventory drops below 50 units, so that I can reorder before we go out of stock.

**Support:**
> As a **support agent**, I want to see a customer's full order history when I open a case, so that I can resolve issues without asking them to repeat information.

## Acceptance Criteria

Each story needs acceptance criteria — the specific conditions that make it "done."

Example for the sales rep story:
- Open opportunities display on the Account record page
- Opportunities are sorted by close date, soonest first
- Clicking an opportunity opens the full record

## Given / When / Then

Given/When/Then (GWT) is a structured way to write acceptance criteria. Instead of a bullet list, each condition is framed as a scenario with three parts:

- **Given** — the starting state or context before anything happens
- **When** — the action the user takes or the event that occurs
- **Then** — the expected result

This format is powerful because it forces you to think about edge cases and makes it impossible to write vague criteria. Developers and QA testers can read a GWT scenario and know exactly what to build and how to test it.

**Same sales rep story written in GWT:**

> **Given** a sales rep opens an Account record that has open opportunities
> **When** the page loads
> **Then** all open opportunities are displayed on the record page, sorted by close date with the soonest first

> **Given** a sales rep is viewing the opportunities list on an Account
> **When** they click on an opportunity
> **Then** the full opportunity record opens

> **Given** an Account has no open opportunities
> **When** a sales rep opens that Account record
> **Then** the opportunities section shows an empty state with the message "No open opportunities"

Notice that third scenario — a bullet list of acceptance criteria often misses the empty/edge case entirely. GWT forces you to ask "what happens when things don't go as expected?"

**SoundCraft Operations example in GWT:**

> **Given** warehouse inventory for a speaker model drops to 49 units
> **When** the inventory is updated in the system
> **Then** an alert is automatically sent to the warehouse manager

> **Given** the warehouse manager has already been alerted for a specific model
> **When** inventory drops further
> **Then** no duplicate alert is sent

## What Makes a Bad User Story

- Too vague: *"As a user, I want the system to be better"*
- Too technical: *"As a dev, I want to refactor the API layer"*
- No clear benefit: *"As a manager, I want a dashboard"*
