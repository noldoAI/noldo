# 🦉 Noldo.ai — Internal Master Protocol
**Version:** 1.0 (Private Beta)
**Objective:** Build the world's most aggressive intent-detection engine.

---

## 🎯 1. The North Star (Mission)
We are **not** building a social listening tool (like Sprout Social or Mention). Those are "Vitamins" used for vanity metrics.
We are building a **Revenue Weapon (Painkiller)**.

* **Our Only Metric that Matters:** `Leads Generated Per User (LGPU)`.
* **The Core Philosophy:** "Don't show me data. Show me who to sell to, and write the message for me."

---

## ⚙️ 2. The Core Product Logic (The "Dual Engine")
Development must strictly separate the backend logic into these two distinct pipelines.

### 🔴 Engine A: The Competitor Poach (Red Mode)
* **Input:** User inputs a `Competitor Name` (e.g., Salesforce).
* **Logic:**
    1.  Monitor Subreddits (r/SaaS, r/Sales) for the brand name.
    2.  **Sentiment Filter:** Discard positive/neutral mentions. Keep only `Negative` sentiment.
    3.  **Context Filter:** Must contain specific trigger words (`expensive`, `slow`, `down`, `buggy`, `switch`).
* **Output:** "Hot Lead" flagged for immediate intervention.

### 🔵 Engine B: The Problem Trap (Blue Mode)
* **Input:** User inputs a `Workflow/Pain` (e.g., Manual Data Entry).
* **Logic:**
    1.  Monitor broader industry subreddits.
    2.  **Semantic Search:** Look for "Help me" signals (`how to automate`, `sick of doing`, `best tool for`).
    3.  **Solution Gap:** Identify posts with high upvotes but *no clear solution* in comments.
* **Output:** "Opportunity" flagged for education-first outreach.

---

## 🏗️ 3. Technical Architecture (High Level)

### A. Data Ingestion Layer
* **Source:** Reddit API / Scrapers (Puppeteer fallback).
* **Frequency:** Real-time (Active Polling) for "Meltdown Alerts." Hourly for standard keywords.
* **Storage:** Raw JSON dumps of threads $\rightarrow$ MongoDB.

### B. The Intelligence Layer (The "Brain")
* **Step 1 (Noise Filter):** Lightweight NLP model to discard 90% of irrelevant posts (memes, news).
* **Step 2 (Intent Scoring):** OpenAI/Anthropic API call to grade remaining posts from 0-100 on "Purchase Intent."
    * *Threshold:* Only display leads with score > 75 to the user.
* **Step 3 (Draft Generation):**
    * If `Intent > 85`: Generate "Trojan Horse" reply (Value first, product second).

### C. The Frontend (The "Terminal")
* **Stack:** Next.js, Tailwind CSS, Shadcn UI.
* **Aesthetic:** Dark Mode, High Contrast, Monospace Data, "Stock Market" visualization.
* **Critical UX:** One-click "Copy Draft" button.



---

## 🤖 4. The "Trojan Horse" Prompt Strategy
*Strict guidance for Prompt Engineering Team.*

The AI must **never** sound like a bot.
* **❌ Bad Output:** "Hello! I saw you hate Jira. Try Noldo, it is better." (Instant Ban).
* **✅ Good Output:** "I ran into that same lag issue with Jira sprints last month. It's usually a caching error. I ended up switching to [Noldo] for our team which fixed the load times, but if you want to stay on Jira, try clearing your project cache." (Helpful + Soft Sell).

---

## 💰 5. Monetization & Business Logic

### The "Hook" (Free Tier / Lead Magnet)
* **Goal:** User Registration.
* **Feature:** "The Meltdown Alert."
    * User can track *one* competitor.
    * If that competitor has a spike in negative sentiment (server outage), we email the user immediately.
    * *Why:* This builds trust and urgency.

### The "Product" (Pro Tier - $99/mo)
* **Goal:** MRR.
* **Feature:** Unlimited "Intent Scanning."
* **Feature:** The "AI Reply Writer."
* **Feature:** Access to "Budget Detection" (posts where users mention specific $ amounts).

### The "Scale" (Enterprise - Custom)
* **Goal:** High LTV.
* **Feature:** API Access (Pipe leads directly into their HubSpot/Salesforce).
* **Feature:** "Team Hunting" (Multiple seats).

---

## 🗺️ 6. Roadmap (Phases)

### Phase 1: The MVP (Current Focus)
* [ ] Reddit Ingestion Pipeline operational.
* [ ] Basic Keyword Matching (No AI yet).
* [ ] Frontend: "Dark Finance" Dashboard.
* [ ] Auth & Stripe Integration.

### Phase 2: The "Smart" Layer (Next 30 Days)
* [ ] Integrate LLM for "Intent Scoring" (Filter the noise).
* [ ] Build "Trojan Horse" Reply Generator.
* [ ] Implement "Meltdown" Push Notifications.

### Phase 3: The Ecosystem (Q2 Goal)
* [ ] Slack/Discord Webhooks (Send leads to where the user works).
* [ ] Chrome Extension (Overlay Noldo data directly on Reddit.com).

---

## ⚠️ 7. Risks & Mitigations

* **Risk:** Reddit API pricing/blocking.
    * *Mitigation:* Build a diversified scraper network; explore intent data from Twitter/X and LinkedIn as backups.
* **Risk:** Users getting banned for spamming.
    * *Mitigation:* Implement daily reply limits in the UI. Force "Review" step before sending.
* **Risk:** "Empty State" (User searches for niche with no data).
    * *Mitigation:* If no live data, show historical data (Last 90 Days) so the dashboard never looks broken.
