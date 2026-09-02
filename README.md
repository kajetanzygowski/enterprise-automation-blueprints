# Enterprise Process Automation & AI Integration Blueprints

A production-ready collection of automated business workflows built with **n8n** and **Make.com**, integrating LLM reasoning (OpenAI GPT-4o, Google Gemini), deterministic data pipelines, external APIs, and CRM platforms.

## Projects Overview

| # | Project | Platform | Core Stack | Key Capabilities |
|---|---|---|---|---|
| **01** | [WhatsApp AI Booking Assistant](./01-whatsapp-ai-booking-assistant/) | Make.com | Gemini Flash, Twilio, Google Calendar, Sheets | Multi-turn memory, calendar slot validation, WhatsApp booking [source: 4]. |
| **02** | [SEO Keyword Gap Analysis Pipeline](./02-seo-keyword-gap-analysis/) | n8n | OpenAI GPT-4o, Senuto API, JavaScript, Regex | API pagination, static data caching, deterministic entity filtering, NLP [source: 5]. |
| **03** | [AI Lead Qualifier & Routing Engine](./03-ai-lead-scoring-real-estate/) | n8n | Gemini 2.0 Flash, Typeform, Twilio, Sheets | Structured JSON lead scoring, multi-path conditional routing, instant SMS alerts [source: 9]. |
| **04** | [Autonomous Infographics Orchestrator](./04-infographics-orchestrator-vision-qc/) | n8n | GPT-4o Vision, DALL·E 3 / gpt-image, WordPress API | Parent/Child architecture, batch processing, automated AI-vision quality control with retry loops [source: 6, 7]. |

## Architecture Principles
* **Deterministic Filtering First:** Heavy computational tasks and entity pruning rely on regex and standard JavaScript before invoking LLMs to optimize execution time and API spend [source: 5].
* **Structured Output Enforcement:** Strict schema definitions and JSON mode enforcement ensure reliable downstream branch execution [source: 5, 9].
* **Defensive Design:** Built-in error handling, execution retries, and clean logging [source: 5, 6, 7].
