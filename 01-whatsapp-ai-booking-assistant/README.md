# Autonomous WhatsApp AI Booking Assistant (Make.com & Gemini)

An automated customer intake and appointment scheduling pipeline integrating WhatsApp messaging, LLM reasoning, real-time Google Calendar availability checks, and Google Sheets CRM persistence.

---

## Business Problem
Service businesses (e.g., automotive repair shops, clinics) suffer from high lead response latency and manual overhead when qualifying incoming client inquiries and coordinating calendar appointments outside business hours.

---

## Solution Overview
This automation serves as an autonomous 24/7 front-desk assistant:
1. Receives incoming WhatsApp messages via Twilio webhooks.
2. Retrieves conversation history from Google Sheets to maintain conversational context.
3. Checks live Google Calendar events within working hours for the upcoming 7 days to detect open slots.
4. Executes structured prompts using **Google Gemini Flash**, strictly validating vehicle data (Make, Model, 17-character VIN) and client details before offering available time slots.
5. Emits structured payloads upon confirmation to automatically insert calendar bookings, update the CRM, and send SMS/WhatsApp confirmations.

---

## Visual Architecture
*(Insert Make.com Scenario Screenshot Here)*

---

## Tech Stack & Integrations
* **Platform:** Make.com
* **AI Engine:** Google Gemini Flash (`gemini-flash-latest`)
* **Messaging & Gateways:** Twilio (WhatsApp Messaging API)
* **Databases & Calendars:** Google Sheets, Google Calendar API
* **Control Flow:** Built-in Router, Text Aggregators, Date/Time Parsing Modules

---

## Key Technical Features
* **State & Memory Management:** Aggregates past interaction bundles using `TextAggregator` to deliver multi-turn memory to the LLM.
* **Dynamic Slot Availability:** Queries the Google Calendar API within a rolling window (`timeMin: {{now}}`, `timeMax: {{addDays(now; 7)}}`) and parses busy intervals to prevent double-booking.
* **Deterministic Output Parsing:** The LLM injects a strict tracking delimiter (`[DANE_DO_ZAPISU: YYYY-MM-DD HH:mm | ...]`), allowing a downstream Router filter to conditionally commit bookings and trigger SMS confirmations only upon definitive scheduling events.

---

## Business Impact
* **Zero Response Lag:** Immediate 24/7 intake for customer inquiries.
* **Data Integrity:** Enforces validation rules (e.g., 17-character VIN requirement) before calendar slots are allocated.
* **Zero Double-Bookings:** Direct validation against live Google Calendar data eliminates scheduling conflicts.
