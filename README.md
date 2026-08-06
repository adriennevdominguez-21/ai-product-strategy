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
| **The Pitch** | M6 | [Complete] | `06-the-pitch/` |

---

## The Bet (M1)

**What we're building, for whom, why now.**

- **Product:** An AI-powered decision support platform that helps educators identify attendance risks earlier, automate routine tasks, and recommend timely interventions to improve student outcomes.
- **AI Value Archetype:** Oracle – Attendance Insight uses AI to analyze attendance and related student data to predict attendance risks, identify emerging trends, and recommend timely interventions that help educators make better decisions.
- **Vulnerability Scores:** _(Moat 4/5 · Data 4/5 · Platform 2/5)_
- **Top Risk:** Platform Exposure
- **Confidence:** _(M)_
- **Prototype:** [View the prototype](https://k12-attend-ai.lovable.app/)
- **Kill Criteria:**

At the end of a **90-day pilot**, we will stop expansion or materially redesign Attendance Insight if:

- **Accuracy:** The system does not achieve at least **90% accuracy** on the approved golden dataset or fails any critical safety test.
- **Adoption:** Fewer than **60% of pilot educators** use the product weekly or accept or meaningfully modify its recommendations.
- **Intervention execution:** Fewer than **80% of assigned interventions** have a documented action and outcome.
- **Attendance impact:** The pilot group does not show at least a **5% improvement in attendance outcomes** compared with its baseline or a matched comparison group.
- **Trust:** Fewer than **75% of participating educators** report that the recommendations are understandable, useful, and trustworthy with human review.

Any critical safety, privacy, fairness, or unauthorized-action failure triggers an immediate pause regardless of the other pilot results.

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

**Reliability Target:**
  
| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | 90% | Weekly evaluation using a dataset of 300 golden test cases (including adversarial examples), scored with rule-based validation and LLM-as-a-judge. Ship only if overall accuracy is ≥90% and no critical safety tests fail. | <85% → trigger gold-set audit |
| Hallucination rate | <1% | eekly evaluation on 300 golden test cases using Rule + LLM-as-a-judge to identify unsupported or fabricated claims. | >3% → auto-rollback to last good model |
| Latency (p95) | <2s | Monitor median response time weekly across production requests. | > 5s → page on-call |
| Drift velocity | <0.5%/4w | Weekly monitoring of production data against the training dataset using drift detection metrics. | >2%/4w → trigger gold-set audit |

- **Golden Dataset:** 5 rows, 2 adversarial
- **Confidence UX:**
**Approach:** Attendance Insight combines tiered confidence, visible uncertainty, and human-in-the-loop review so educators can understand how reliable each recommendation is and remain responsible for final intervention decisions.

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

**Compounding System:** 
| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Educator acceptance, modification, or rejection of AI recommendations; intervention selections; intervention outcomes; attendance improvements; corrected risk classifications; and reviewer feedback | Better risk predictions, more relevant intervention recommendations, improved confidence calibration, expanded golden-dataset coverage, and stronger personalization to district workflows. | Y | active |
| Cross-Domain Transfer | Attendance history combined with grades, behavior incidents, enrollment data, demographics, intervention history, school-level trends, and district attendance policies. | More contextual risk assessments, identification of relationships across student outcomes, improved recommendations across schools and grade levels, and earlier detection of emerging attendance risks. | Y | active |
| Network Intelligence | Privacy-preserving and anonymized attendance patterns, intervention outcomes, benchmarks, and educator feedback contributed by multiple districts. | anonymized attendance patterns, intervention outcomes, benchmarks, and educator feedback contributed by multiple districts.Cross-district benchmarks, broader pattern recognition, identification of effective interventions across comparable student populations, and improved predictions for every participating district. | Y | broken |

## Shadow AI Audit
 
| Workaround | Signal Source | Signal Type | Frequency | Spend ($/mo) | Decision |
|---|---|---|---|---:|---|
| Exporting attendance data into general-purpose AI tools to create student and school summaries | User interview | Capability gap | H | $100/mo | Build |
| Using Zapier or Make to send risk alerts and intervention reminders through email or team messaging | Zapier/Make | Workflow gap | H | $100/mo | Partner |
| Building custom dashboards and risk models through the Attendance Insight API | API pattern | Capability gap | M | $1,000/mo | Build |
| Using external translation AI to draft multilingual family outreach | Support ticket | Capability gap | M | $200/mo | Partner |
| Creating independent chatbots that answer general attendance-policy questions | Sales call | Pricing gap | L | $100/mo | Ignore |

- **Agent Boundaries:** _Not shipping agents this version._
- **Regulatory Exposure:** ERPA, COPPA, State student-privacy laws, Title VI and Title IX, Section 504, ADA, and IDEA. Risk tier: high. Controls: Attendance Insight uses role-based access, encryption, audit logs, data minimization, retention limits, vendor controls, and FERPA-compliant handling of student records. It also requires human approval for consequential decisions, monitors accuracy and demographic performance, supports corrections and appeals, and prohibits fully automated disciplinary, legal, enrollment, or accommodation decisions.

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now):**

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Detect students at risk of chronic absenteeism | ≥90% golden-set accuracy with no critical safety failures | M |
| Explain each risk classification and communicate uncertainty | ≥80% of educators report that risk drivers and confidence are understandable | H |
| Distinguish excused, medical, disability-related, and unexcused absences | 100% of absence-type safety tests pass | H |
| Block predictions based on missing, duplicate, delayed, or conflicting data | 100% of known data-quality conflicts trigger human review | H |
| Require human approval for consequential student actions | 100% of high-impact interventions receive documented human approval | H |
| Expand the golden dataset and implement reliability monitoring | 300 representative test cases; weekly monitoring of accuracy, hallucination, latency, drift, overrides, and fairness | H |
| Validate intervention recommendations and configurable risk alerts | ≥60% recommendation acceptance or modification rate; ≥40% of alerts lead to review or action | M |

- **Horizon 2 (Next):**

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Track intervention completion and attendance outcomes | ≥80% of assigned interventions have a recorded outcome | M |
| Use educator corrections and intervention outcomes for recursive learning | Measurable model improvement across two consecutive evaluation cycles | M |
| Build configurable district policy and intervention workflows | Launch with at least three district policy configurations and ≥70% administrator satisfaction | M |
| Integrate multilingual family outreach through an approved translation partner | ≥95% translation approval rate after educator review with no unauthorized automatic sends | M |
| Validate hybrid AI Premium pricing with district buyers | At least three pilot districts accept pricing or provide documented willingness-to-pay evidence | M |


- **Horizon 3 (Bet):**

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Launch privacy-preserving cross-district benchmarking and federated learning | At least five districts participate with no identifiable student data leaving district boundaries | L |
| Optimize interventions using anonymized cross-district outcomes | Demonstrate a statistically meaningful improvement in recommendation effectiveness over district-only models | L |

- **Board Narrative:** **The case:**

1. Why now: Chronic absenteeism requires earlier and more targeted intervention, while districts now have the data and AI capabilities needed to move from retrospective reporting to proactive decision support.
2. What's defensible: District-specific policy intelligence, deeply integrated intervention workflows, educator feedback, longitudinal outcomes, and a future privacy-preserving learning network create context and switching costs that general AI tools cannot easily replicate.
3. The economics: A $45 per-user platform fee plus $0.03 per AI request produces an estimated $60 in monthly revenue against $19 in monthly COGS, increasing gross margin from 64% to 68% and gross profit by $11 per user per month.


- **Ask:**
Approve $1.8 million and eight dedicated employees for 12 months, with a 90-day release gate, to complete the reliability foundation, integrate district data, and run pilots with two to three districts. The team will include one product manager, two ML engineers or data scientists, two full-stack engineers, one data-integration engineer, one MLOps and security engineer, and one education implementation and research lead. Funding this means pausing native multilingual outreach and other non-core chatbot or custom-dashboard work, using partners where necessary, and withholding investment in federated learning until the pilots validate outcomes and demand.

- ## M1 Baseline vs. Now

*Your 3-sentence AI strategy from Module 1 vs. what you'd say now:*

**M1 baseline:** Attendance Insight is an AI-powered decision-support platform that helps educators identify attendance risks earlier and recommend timely interventions. It analyzes attendance and related student data to predict risk, identify trends, and improve educator decision-making. We would stop investing if the AI fails to improve risk identification, attendance outcomes, or user trust and adoption.

**Now:** Attendance Insight is a high-governance attendance intelligence platform that combines explainable predictions, district-specific policy context, and human-approved interventions to improve measurable student outcomes. Our near-term priority is proving the bet through a controlled district pilot, a 300-case golden dataset, and explicit reliability, fairness, adoption, and outcome thresholds. If validated, intervention outcomes and privacy-preserving cross-district learning will create a defensible data flywheel while hybrid pricing supports sustainable AI economics.

- **Key Strategic Change:**
Attendance Insight has evolved from a broad AI prediction concept into a measurable, high-governance product strategy built around human accountability, district-specific workflows, explicit validation thresholds, sustainable economics, and a defensible learning loop based on intervention outcomes.

→ Details: [`06-the-pitch/`](06-the-pitch/)
