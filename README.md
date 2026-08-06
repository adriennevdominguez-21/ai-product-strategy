# Attendance Insight
>An AI-powered decision support platform that helps educators identify attendance risks earlier, automate routine tasks, and recommend timely interventions to improve student outcomes.

> We are building an AI-powered attendance intelligence platform for K–12 school leaders that transforms attendance data into proactive insights and recommendations, enabling earlier interventions to improve student outcomes.

---

## Strategy at a Glance

| Component | Module | Status | Key Artifact |
|-----------|--------|--------|-------------|
| **The Bet** | M1 | [Complete] | `01-the-bet/` |
| **The Moat** | M2 | [Complete] | `02-the-moat/` |
| **The Margin** | M3 | [Complete] | `03-the-margin/` |
| **The Contract** | M4 | [Complete] | `04-the-contract/` |
| **The Guardrails** | M5 | [Complete] | `05-the-guardrails/` |
| **The Pitch** | M6 | [x] | `06-the-pitch/` |

---

## The Bet (M1)

**What we're building, for whom, why now.**

- **Product:** An AI-powered decision support platform that helps educators identify attendance risks earlier, automate routine tasks, and recommend timely interventions to improve student outcomes.
- **AI Value Archetype:** Oracle – Attendance Insight uses AI to analyze attendance and related student data to predict attendance risks, identify emerging trends, and recommend timely interventions that help educators make better decisions.
- **Vulnerability Scores:** _(Moat 4/5 · Data 4/5 · Platform 2/5)_
- **Top Risk:** Platform Exposure
- **Confidence:** _(M)_
- **Prototype:** [View the prototype](https://k12-attend-ai.lovable.app/)
- **Kill Criteria:** We would stop investing in this product if the AI consistently fails to improve the accuracy of identifying at-risk students, does not lead to measurable improvements in attendance or intervention outcomes, or if users do not trust or adopt the AI recommendations despite iterative improvements.

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this won't get copied in 6 months.**

- **Data Flywheel Score:** 16/20
- **Weakest Loop:** Network Loop (3/5)
- **Top Encroachment Threat:** PowerSchool
- **Encroachment Defense:** Attack vector (target the weakest loop): Launch a privacy-preserving, federated AI model that learns from anonymized attendance patterns across participating districts without exposing student data, turning Attendance Insight's siloed data into PowerSchool's competitive advantage.

Weeks 1-4 - what they ship: Release AI-powered attendance risk prediction, intervention recommendations, and district benchmarking trained on anonymized data from thousands of schools while ensuring no student-level data leaves a district.

Weeks 5-8 - how they poach users: Offer the new AI capabilities at no additional cost to existing PowerSchool customers, emphasizing that districts benefit from insights learned across the network while maintaining FERPA compliance and data privacy.

Weeks 9-12 - why users don't come back: Districts begin receiving more accurate predictions and stronger intervention recommendations because the AI continuously learns from cross-district outcomes, making Attendance Insight's siloed models appear less effective over time.

Your defense: Build a privacy-preserving federated learning network that allows districts to securely contribute anonymized outcomes, while differentiating through explainable AI, configurable intervention workflows, and district-specific policy intelligence that delivers both network-wide and local insights.
- **Vendor Portability:** Partial

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)

**Will this make money or bleed it?**

- **Gross Margin (current):** 64%
- **Gross Margin (AI-adjusted):** 68%
- **Pricing Model:**
**Current pricing:** Enterprise SaaS subscription licensed annually by school district.

**Proposed AI pricing:** AI Premium add-on that includes predictive attendance intelligence, intervention recommendations, and district benchmarking.

| Pricing Component | Value |
|-------------------|-------|
| **Strategy Posture** | **Maximize** – Optimize revenue by pricing for measurable district value while keeping AI costs aligned with usage. |
| **Pricing Model** | **Hybrid (Platform Fee + Metered AI Work)** |
| **Unit of Work Metered** | AI requests (predictions, recommendations, explanations, and copilot interactions) |
| **Base Fee** | **$45 per user/month platform subscription** |
| **Price per Unit** | **$0.03 per AI request** |
| **Estimated Units/User/Month** | **500 AI requests** |
| **Implied Revenue/User/Month** | **$60.00** |

- **Pricing Today → Tomorrow:** Enterprise SaaS subscription licensed annually by school district. → AI Premium add-on that includes predictive attendance intelligence, intervention recommendations, and district benchmarking.
- **Total AI COGS / unit:** $19.00
- **Cascading Strategy:** Triage: GPT-4.1 Mini (or equivalent low-cost model); frontier: GPT-5 (or equivalent frontier reasoning model); ratio **80% triage / 20% frontier**
- **Net Margin Shift:**
- 
| Metric | Value |
|--------|------:|
| **Δ Margin %** | **+4 percentage points** |
| **Δ Gross Profit** | **+$11.00 per user/month** |

- **Break-even at:**
- 100 AI requests per user per month.

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users will trust a probabilistic system.**

- **Reliability Target:**
  | Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | 90% | Weekly evaluation using a dataset of 300 golden test cases (including adversarial examples), scored with rule-based validation and LLM-as-a-judge. Ship only if overall accuracy is ≥90% and no critical safety tests fail. | <85% → trigger gold-set audit |
| Hallucination rate | <1% | eekly evaluation on 300 golden test cases using Rule + LLM-as-a-judge to identify unsupported or fabricated claims. | >3% → auto-rollback to last good model |
| Latency (p95) | <2s | Monitor median response time weekly across production requests. | > 5s → page on-call |
| Drift velocity | <0.5%/4w | Weekly monitoring of production data against the training dataset using drift detection metrics. | >2%/4w → trigger gold-set audit |

- **Golden Dataset:** 5 rows, 2 adversarial
- **Confidence UX:**
- **Approach:** Attendance Insight combines tiered confidence, visible uncertainty, and human-in-the-loop review so educators can understand how reliable each recommendation is and remain responsible for final intervention decisions.

**Confident (>90%):** Generates a risk classification, explains the strongest contributing factors, and recommends a prioritized intervention.

**Uncertain (50-90%):** Provides a provisional risk assessment and presents multiple possible explanations or interventions. Shows visible uncertainty, missing or conflicting factors, and a prompt to review the recommendation.

**Not confident (<50%):** Avoids making a definitive prediction or automatically recommending a high-impact action. Provides low-confidence warning, explanation of why confidence is limited, and the data needed to improve the assessment.

**User control surface:** 

Accept, modify, or dismiss the recommendation; assign an intervention;

- Users see AI reasoning / drivers
- Users correct & override outputs
- Corrections feed back into the model / dataset
- Users adjust the confidence threshold _(not yet)_
- 
- **HITL Architecture:** **Trigger:** Human review is triggered for predictions with confidence below 60% or any high-impact student intervention recommendation.
- **Failure Mode Coverage:** *What failure mode did your partner find that you missed?*
- My partner found that Attendance Insight could treat excused and unexcused absences the same, causing students with legitimate medical, disability-related, or approved absences to be incorrectly classified as high risk. Our original golden dataset missed this failure because it tested absence counts without including absence type or accommodation context.

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales, and what compounds.**

- **Compounding System:** | Loop | Input | Output | Compounds? | Status | |------|-------|--------|-----------|--------| | Recursive Learning | Educator acceptance, modification, or rejection of AI recommendations; intervention selections; interv…
- **Governance Posture:** AI features within Attendance Insight, including attendance-risk predictions, intervention recommendations, confidence scores, explanations, prioritized alerts, automated summaries, and the conversational attendance assi…
- **Autonomy Boundaries:** Generate summaries, detect attendance trends, prioritize dashboard alerts, calculate risk indicators, and recommend possible interventions., auto.…
- **Escalation Triggers:** 1. AI confidence is below 60%.
- **Audit Cadence:** Weekly, AI confidence is below 60%. Source data contains missing, conflicting, duplicate, or delayed records.…
- **Shadow AI Audit (user-side):**
- **Agent Boundaries:** _Not shipping agents this version._
- **Regulatory Exposure:** FERPA, COPPA, State student-privacy laws, Title VI and Title IX, Section 504, ADA, and IDEA. Risk tier: high. Controls: Attendance Insight uses role-based access, encryption, audit logs, data minimization, retention limi…

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now):**
- **Horizon 2 (Next):**
- **Horizon 3 (Bet):**
- **Board Narrative:** **The case:**
- **Ask:** ## M1 Baseline vs. Now
- **Key Strategic Change:**

→ Details: [`06-the-pitch/`](06-the-pitch/)
