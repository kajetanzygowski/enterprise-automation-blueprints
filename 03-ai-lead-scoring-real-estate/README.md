# Real Estate AI Lead Qualification & Conditional Routing (n8n & Gemini)

An automated inbound lead processing workflow that scores web leads in real-time, updates CRM records, and triggers multi-channel notifications based on deal readiness [source: 9].

## Core Workflow Steps
1. **Webhook Intake:** Ingests raw lead submissions from Typeform webhooks [source: 9].
2. **Payload Extraction:** Extracts contact details, budget constraints, timeline, and purchase purpose [source: 9].
3. **AI Classification:** Evaluates lead temperature (`HOT`, `WARM`, `COLD`) and outputs a numerical readiness score (1-10) using Gemini Flash [source: 9].
4. **Deterministic Switch Node:** Evaluates the AI classification to trigger separate fulfillment paths [source: 9].
5. **Multi-Channel Fulfillment:**
   * **HOT Leads:** Instant SMS alert to the sales broker via Twilio + personalized client confirmation email + CRM record update [source: 9].
   * **WARM / COLD Leads:** Automated nurture confirmation emails + logging to separate CRM views [source: 9].

## Technical Highlights
* Strict zero-shot prompt formatting returning clean JSON without markdown code fences [source: 9].
* Atomic database append-or-update operations based on phone number matching [source: 9].
