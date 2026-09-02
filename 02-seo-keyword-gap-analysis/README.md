# Production-Grade SEO Keyword Gap Analysis Pipeline (n8n & OpenAI)

An automated high-throughput data analysis engine that identifies commercial keyword gaps against competitors using Senuto APIs, custom JavaScript data processing, and LLM relevance evaluation [source: 5].

## Core Workflow Steps
1. **Input Normalization:** Sanitizes input domains and competitor lists using custom JS [source: 5].
2. **Dynamic Domain Research:** Conducts live web research via OpenAI web search to extract the client's business niche and commercial profile [source: 5].
3. **Data Harvesting & Expansion:** Queries Senuto APIs for related keywords and competitor positioning with full pagination and batching controls [source: 5].
4. **Data Aggregation & Deduplication:** Normalizes search volume, strips diacritics, groups semantic duplicates, and filters out terms already in the client's Top 50 rankings [source: 5].
5. **Deterministic Entity Filter:** Evaluates thousands of phrases against cached entity lists (cities, streets, personal names, brands) to strip non-commercial keywords before LLM ingestion [source: 5].
6. **LLM Relevance & Export:** Chunks surviving phrases into batches for GPT-4o validation, generating a final sorted CSV report [source: 5].

## Technical Highlights
* **Global Static Data Cache:** Uses `$getWorkflowStaticData('global')` to persist entity whitelists and API error states across executions [source: 5].
* **Cost-Optimization Architecture:** Reduces LLM token consumption by over 70% by using regex rules and volume thresholds prior to OpenAI calls [source: 5].
