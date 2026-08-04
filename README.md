

# DevSynt AI Automation Internship

DevSynt AI Automation Internship – Summer 2026

This repo contains my weekly task progress, notes, and screenshots for the AI Automation track.

## Project 1 — SlotWise: AI Booking Concierge Bot

**Platform:** Discord (chosen since Telegram is restricted in Pakistan)

SlotWise is a conversational booking bot for a restaurant/parlour, built entirely in n8n:

- **Greeting:** Bot asks if the user wants to book or has a question
- **Intent detection:** A Groq LLM (`llama-3.1-8b-instant`) classifies the reply into `booking`, `question`, or `handoff`
- **Booking flow (if intent = booking):**
  - Service/type selection (table size or parlour service)
  - Preferred timing
  - Offer of 2-3 mock time slots
  - Confirmation message with a full booking summary
- **Logging:** Every confirmed booking is appended as a new row in a connected Google Sheet (name, service, date/time, slot, status)
- **Handoff:** If intent isn't a clear booking request, the bot replies with a handoff message directing the user to the team

**Files:**
- `project1/workflow.json` — exported n8n workflow
- `project1/workflow-canvas-screenshot.png` — visual of the connected node canvas

**Setup note:** This repo does not include the Discord bot token, Groq API key, or Google OAuth credentials (never commit these). To run this workflow yourself, add your own credentials in n8n for the Discord, HTTP Request (Groq), and Google Sheets nodes.

## Author

Amna Bibi
