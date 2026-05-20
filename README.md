**Project:** Analysis of AI Overviews Impact on Organic Traffic

**Period:** January 2025 – May 2026
**Tech Stack**: Google Search Console, Python (Log Parsing), Power BI, DAX
**GitHub: [**Link to repository]
**Live Power BI Dashboard (ROI Simulator): [ [LINK POWER BI](https://app.powerbi.com/view?r=eyJrIjoiZjY3MGFiYzQtZGRlMi00YTRlLWIwMzYtYWNkZmYzMTJiYzA2IiwidCI6IjdlNzU4MmI2LWUyYWEtNDU1Yy04MzUyLWJlOWZkNGE0MTFkZCIsImMiOjh9)]**

https://app.powerbi.com/view?r=eyJrIjoiZjY3MGFiYzQtZGRlMi00YTRlLWIwMzYtYWNkZmYzMTJiYzA2IiwidCI6IjdlNzU4MmI2LWUyYWEtNDU1Yy04MzUyLWJlOWZkNGE0MTFkZCIsImMiOjh9

---

## PART 1: INTRODUCTION

**About CiaoRentCar**
CiaoRentCar is a car and scooter rental platform operating in major Italian cities (primarily Milan, Bergamo, and Naples).

**Key specialization:** Affordable vehicle rentals with flexible payment options, including cash deposits for customers without credit cards.

**Website Relaunch (April 2026):**
Complete redesign and launch of a new, reservation-optimized website, replacing the old booking system.

**EXECUTIVE SUMMARY**

This analytical project evaluates the impact of Artificial Intelligence (Google AI Overviews / SGE) on the organic traffic of an Italian car rental company.

In addition to diagnosing SEO traffic cannibalization, the project addresses the lack of reliable financial data in the CRM and proposes a new, passive revenue stream — a **B2B API** model based on monetizing AI scraper traffic.

The introduction of Google’s AI Overviews (SGE) fundamentally changed the architecture of organic search. CiaoRentCar, an Italian vehicle rental platform, experienced the **“SGE Paradox”**: despite a significant improvement in average ranking position (+43%), the overall Click-Through Rate (CTR) dropped by nearly 23%.

This report diagnoses the phenomenon using server log analysis and search intent segmentation. It also presents an interactive financial model in Power BI that justifies the implementation of a data monetization strategy (paid API for LLM bots), projecting a strong **ROI of +444%**.

### Business Challenges

1. **Decline in SEO Effectiveness (AI Cannibalization)**
Significant drop in Click-Through Rate (CTR) despite stable or growing number of impressions in Google Search Console. Users are receiving direct answers from AI Overviews and leaving without visiting the website.
2. **Infrastructure Costs (Parasitic Bot Traffic)**
Server logs (NGINX) revealed a dramatic increase in requests from LLM bots (ClaudeBot, GPTBot, and others) that freely scrape real-time pricing and availability data.
3. **Missing Financial Data in CRM**
The booking database extract (bookings_anon.csv) was heavily anonymized — transaction amounts and return dates were removed, making it impossible to calculate profitability per vehicle.

---

### PART 1: HYPOTHESIS AND DATA

**Main Cause: AI Overviews (SGE)**

Google Search Generative Experience (SGE) / AI Overviews generates AI-powered answers that appear above traditional organic results. When a user searches for *"noleggio scooter milano"*, they now see:

1. **AI Overview** ← Direct answer at the top
2. Traditional organic results ← Where CiaoRentCar appears
3. Paid ads ← Below

**Result:** Users get the information they need from AI and often don’t click through to any website.

---

**One year after the European launch of SGE (March 2025),** we observed a contradictory trend:

- **✅ Ranking:** Improved from 26 → 15 (+43%)
- **✅ Impressions:** +71.6%
- **✅ Clicks:** +46.3%
- **❌ CTR:** -13.1%

**This is the classic SGE Paradox** — better visibility, but significantly lower traffic.

---

**Traffic Composition (Dominance of Agentic Commerce)**

Analysis of server logs using a custom Python script (User-Agent parsing) showed that AI bots are crawling the website nearly **7 times more frequently** than real users.

- **🤖 AI / Bot Traffic:** 20,647 requests (**86.7%** of total server load)
- **👥 Real User Traffic:** 3,180 requests (**13.3%**)

---

**Search Intent Segmentation (Informational vs Transactional)**

Manual segmentation of Google Search Console data clearly shows where cannibalization is happening:

**Informational queries (🔴 Under strong SGE pressure):**
High rankings but unnaturally low CTR. AI Overviews provide direct answers, eliminating the need to click through to the website.

| Query | Clicks | Impressions | CTR | Position | Risk |
| --- | --- | --- | --- | --- | --- |
| noleggio scooter milano | 591 | 11,602 | 5.09% | 6.81 | 🔴 HIGH |
| noleggio auto senza carta | 82 | 1,360 | 6.03% | 4.17 | 🔴 HIGH |
| affitto scooter milano | 51 | 771 | 6.61% | 6.08 | 🔴 HIGH |
| tabella danni noleggio | 42 | 1,975 | 2.13% | 1.75 | 🔴 CRITICA |

## PART 2: DASHBOARD

**[ [LINK POWER BI](https://app.powerbi.com/view?r=eyJrIjoiZjY3MGFiYzQtZGRlMi00YTRlLWIwMzYtYWNkZmYzMTJiYzA2IiwidCI6IjdlNzU4MmI2LWUyYWEtNDU1Yy04MzUyLWJlOWZkNGE0MTFkZCIsImMiOjh9)]**

INTERACTIVE ROI SIMULATOR (What-If Analysis in Power BI)

https://app.powerbi.com/view?r=eyJrIjoiZjY3MGFiYzQtZGRlMi00YTRlLWIwMzYtYWNkZmYzMTJiYzA2IiwidCI6IjdlNzU4MmI2LWUyYWEtNDU1Yy04MzUyLWJlOWZkNGE0MTFkZCIsImMiOjh9

**The Heart of the Project** is a dynamic financial model built in Power BI — a decision-support tool designed for C-level executives.

### Key Functional Pillars of the ROI Simulator:

1. **Sensitivity Analysis**
Three independent parameters (Monthly API Fee, Bot Adoption Rate, and Organic Conversion Lift) allow users to instantly simulate pessimistic, base, and optimistic scenarios.
2. **Logical Regime (DAX)**
The calculator’s formulas automatically activate revenue streams only in relevant scenarios. Bot API revenue is set to €0 in Scenario A and the blocking option, ensuring logical consistency and preventing unrealistic projections.
3. **Market Risk Mitigation**
The simulator clearly demonstrates that **Scenario B** offers the highest resilience to market fluctuations. Even with lower-than-expected bot adoption, infrastructure savings and increased conversion rates guarantee the fastest break-even point (**2.2 months**).

### Dashboard Contains:

- Current Situation Analysis
- Interactive ROI Calculator
- Scenario Comparison
- Bot Traffic Analysis

**Data Sources:**
Google Search Console, Server Logs (Apache/Nginx), Internal Booking System (bookings_anon.csv).

**Base Assumptions:**
Average Order Value (AOV) = €45, Baseline Conversion Rate = 8%.
Conservative estimates include -20% SGE cannibalization and ±15% forecasting margin of error.

---

### PART 3: SOLUTIONS AND RECOMMENDATIONS

Hard-blocking bots via robots.txt reduces infrastructure costs but generates massive **opportunity cost**. The website disappears from LLM answers, losing the chance to build brand authority in AI-generated responses.

Three adaptive scenarios were developed. Net Profit represents the incremental annual value after deducting fixed and operational costs.

---

**SCENARIO A: Defensive AIO Optimization (AI Search Optimization)**
Focus on becoming the most cited and trusted source in AI Overviews through technical optimization and PR activities.

**Scope:**

- Implementation of Schema.org (LocalBusiness, Product, FAQPage)
- FAQ section restructuring for better AI parsing
- PR & link-building campaign targeting travel blogs

**Costs:** €4,500 (€3,000 PR + €1,500 IT)

**Expected Year 1 Revenue:** €19,375
**ROI:** **+331%Payback Period:** **2.8 months** ✅

---

**SCENARIO B: AIO + Bot API Monetization (RECOMMENDED)**
Combines Scenario A with controlled monetization of AI traffic. Free access for bots is limited (100 queries/day), with a Premium plan (€100/month) for unlimited real-time access to pricing and availability.

**Costs:** €6,500 (€4,500 from Scenario A + €2,000 API development)

**Expected Year 1 Revenue:** €24,475
**ROI:** **+444%Payback Period:** **2.2 months** ✅✅

---

**SCENARIO C: Full Native Integration (LLM Plugins)** – Long-term (Year 2+)
Development of native plugins for ChatGPT and Claude enabling direct bookings within the chat interface (“Rent a car in Milan directly from Claude”).

**Expected Impact (Year 2+):** 10–20% additional bookings + new AI-native revenue stream.
Not recommended for Year 1 implementation.

---

**Financial Summary (Year 1 Forecast):**

| Financial Indicator | Scenario A (AIO Only) | **Scenario B (AIO + Bot API)** ⭐ | Scenario C (Full Integration) |
| --- | --- | --- | --- |
| Implementation Cost (One-time) | €4,500 | €6,500 | €8,500 |
| Gross Incremental Revenue | €19,375 | €24,475 | €32,500 |
| **Net Incremental Profit** | €14,875 | **€17,975** | €24,000 |
| **ROI** | **+331%** | **+444%** | +282% |
| **Payback Period** | 2.8 months | **2.2 months** | 3.1 months |

### APPENDIX: METHODOLOGY

**Data Sources:**

- Google Search Console (January 2025 – May 2026)
- Server Logs (AI bot detection)
- Booking Data (conversion analysis)

**Analytical Tools:**

- Python (pandas, matplotlib)
- Power BI (visualization and interactive modeling)
- Google Sheets (forecasting)

**Key Assumptions:**

- AIO-driven CTR uplift: +8% (conservative)
- SGE Cannibalization rate: -20%
- Conversion rate lift from increased brand authority: +2 percentage points
- Bot API adoption rate: 5% (conservative)

---

### Business Conclusions

Instead of cutting SEO costs, the company should adopt a **dual-track strategy**:

1. **Technical Optimization (AIO)** – Transform the website into the primary and most authoritative source for AI bots, without engaging in a price war.
2. **Monetization of AI Traffic** – Limit free access for AI scrapers and implement a market-appropriate “paywall” for real-time data (pricing and availability).

---

### CONTACT / QUESTIONS

Do you have any questions regarding the analysis, assumptions, or implementation?

**Analysis completed:** May 2026
**Data period:** January 2025 – May 2026
