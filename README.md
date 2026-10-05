# Enterprise Process Automation & AI Integration Blueprints

A collection of reference automation workflows built with **n8n** and **Make.com**, integrating LLM reasoning (OpenAI GPTs, Google Gemini), deterministic data pipelines, external APIs, and CRM platforms.

## Projects Overview

| # | Project | Platform | Core Stack | Key Capabilities |
|---|---|---|---|---|
| **01** | [WhatsApp AI Booking Assistant](./01-whatsapp-ai-booking-assistant/) | Make.com | Gemini Flash, Twilio, Google Calendar, Sheets | Multi-turn memory, calendar slot validation, WhatsApp booking. |
| **02** | [SEO Keyword Gap Analysis Pipeline](./02-seo-keyword-gap-analysis/) | n8n | OpenAI GPT-4o, Senuto API, JavaScript, Regex | API pagination, static data caching, deterministic entity filtering, NLP. |
| **03** | [AI Lead Qualifier & Routing Engine](./03-ai-lead-scoring-real-estate/) | n8n | Gemini 2.0 Flash, Typeform, Twilio, Sheets | Structured JSON lead scoring, multi-path conditional routing, instant SMS alerts. |
| **04** | [Autonomous Infographics Orchestrator](./04-infographics-orchestrator-vision-qc/) | n8n | GPT-4o Vision, DALL·E 3 / gpt-image, WordPress API | Parent/Child architecture, batch processing, automated AI-vision quality control with retry loops. |

## Architecture Principles
* **Deterministic Filtering First:** Heavy computational tasks and entity pruning rely on regex and standard JavaScript before invoking LLMs to optimize execution time and API spend.
* **Structured Output Enforcement:** Strict schema definitions and JSON mode enforcement ensure reliable downstream branch execution.

## Contact

Available for white-label / subcontracting work on n8n and Make.com (remote, NDA welcome).

- Email: kajetanzygowski@gmail.com
- LinkedIn: https://www.linkedin.com/in/kajetan-%C5%BCygowski-3302653a2/
