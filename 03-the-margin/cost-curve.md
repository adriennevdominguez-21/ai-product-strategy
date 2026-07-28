# Cost Curve & Pricing Strategy

---

# Leader–Filler–Killer Framework

## Leader
**AI-powered attendance intelligence** that predicts student attendance risk, explains contributing factors, and recommends timely, evidence-based interventions to help educators improve student outcomes.

## Filler
- AI-generated summaries of district, school, and student attendance trends
- Natural language explanations of attendance risk scores
- Dashboard insights and prioritized alerts
- Suggested intervention plans and follow-up reminders
- Conversational AI assistant for attendance-related questions

## Killer
- Predictive risk modeling using attendance, grades, behavior, demographics, and intervention history
- Explainable AI that identifies key drivers behind attendance risk
- Privacy-preserving federated learning that continuously improves predictions across districts without exposing student data
- AI-powered intervention optimization that recommends the most effective actions based on historical outcomes

## Killer Usage

**20–30% of AI requests**

---


## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|---------------:|-------|
| Inference (primary model) | **$2.40** | Complex attendance risk prediction, explainability, and intervention recommendations |
| Inference (cascading/triage) | **$0.60** | Dashboard summaries, chatbot responses, and simple requests handled by a lower-cost model |
| Infrastructure | **$10.00** | Cloud hosting, monitoring, APIs, networking, and security |
| Data/storage | **$4.00** | Secure student data storage, analytics warehouse, backups, and encryption |
| Human-in-the-loop | **$2.00** | Model evaluation, prompt tuning, QA, and customer support |
| **Total AI COGS** | **$19.00** | Estimated monthly operating cost per active user |

---

## Cascading Strategy

**Triage model:** GPT-4.1 Mini (or equivalent low-cost model)

**Frontier model:** GPT-5 (or equivalent frontier reasoning model)

**Routing rule:** Route summaries, search, FAQs, and dashboard explanations to the triage model. Escalate only complex attendance risk analysis, intervention recommendations, and explainable AI requests to the frontier model.

**Expected cascade ratio:** **80% triage / 20% frontier**

---

## Pricing Model

**Current pricing:** Enterprise SaaS subscription licensed annually by school district.

**Proposed AI pricing:** AI Premium add-on that includes predictive attendance intelligence, intervention recommendations, and district benchmarking.

**Model:** **Hybrid (district subscription + per-user AI licensing)**

---

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3× | Gross margin decreases by approximately 10%. | Increase routing to lower-cost models, optimize prompts, and reserve frontier models for high-value use cases. |
| Heaviest segment doubles | Infrastructure and inference costs increase for large districts. | Introduce enterprise pricing tiers, batch processing, and volume-based licensing. |
| Model provider raises prices 50% | AI operating costs increase, reducing profitability. | Shift workloads to Anthropic, Google Gemini, or Azure OpenAI using the abstraction layer and benchmark quality before migration. |

---

## Board One-Pager

**Before (traditional SaaS):**

Districts purchase attendance dashboards and reporting tools that help educators monitor attendance after problems occur.

**After (AI-enabled):**

Districts subscribe to an AI-powered attendance intelligence platform that predicts attendance risk, recommends evidence-based interventions, and continuously improves through educator feedback and privacy-preserving learning.

**Net margin shift:**

AI introduces additional inference costs that modestly reduce gross margins, but premium pricing, stronger customer retention, improved student outcomes, and differentiated AI capabilities increase long-term customer lifetime value and overall profitability.
