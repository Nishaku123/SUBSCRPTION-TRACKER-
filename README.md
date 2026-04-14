# Subscription Tracker — AI Agent with n8n

A conversational AI agent that logs your recurring subscriptions 
into Google Sheets using natural language.

## How it works

Type something like:
> "I just subscribed to Netflix for ₹999/month"

The agent understands your message, confirms the details, checks 
for duplicates, and logs it — structured and clean.

## Tech Stack

- **n8n** — workflow automation
- **Groq (LLaMA)** — AI chat model
- **Simple Memory** — session context for the agent
- **Google Sheets** — storage backend

## Fields Tracked

| Field       | Example        |
|-------------|----------------|
| Expense     | Netflix        |
| Cost        | ₹999           |
| Cadence     | Monthly        |
| Charge Date | 2026-04-14     |
| Status      | Active         |

## Features

- Natural language input — no forms or UI needed
- Duplicate detection — updates existing entries instead of 
  inserting again
- Structured logging — consistent fields every time
- Memory-aware — agent maintains context within a session

## Setup

1. Import `workflows/subscription_tracker.json` into your n8n instance
2. Connect your Google Sheets account under credentials
3. Add your Groq API key under credentials
4. Update the Sheet ID in the Google Sheets node to point to your sheet
5. Activate the workflow and open the Chat trigger to start tracking

## Environment / Credentials Needed

- `Google Sheets OAuth` — connect your Google account in n8n
- `Groq API Key` — get it from console.groq.com

## Learnings

The most interesting part of this project was refining the agent's 
behavior through prompt engineering — teaching it to plan before 
acting, check before inserting, and update gracefully when a 
subscription already exists.
