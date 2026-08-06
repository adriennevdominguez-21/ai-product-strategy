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
| Inference (primary model) | **$2.25** | Complex attendance risk prediction, explainability, and intervention recommendations |
| Inference (cascading/triage) | **$1.00** | Dashboard summaries, chatbot responses, and simple requests handled by a lower-cost model |
| Infrastructure | **$10.00** | Cloud hosting, monitoring, APIs, networking, and security |
| Data/storage | **$4.00** | Secure student data storage, analytics warehouse, backups, and encryption |
| Human-in-the-loop | **$2.00** | Model evaluation, prompt tuning, QA, and customer support |
| **Total AI COGS** | **$19.25** | Estimated monthly operating cost per active user |

---

## Cascading Strategy

**Triage model:** GPT-4.1 Mini (or equivalent low-cost model)

**Frontier model:** GPT-5 (or equivalent frontier reasoning model)

| Feature | Complexity | Model Tier | Cost / Req | Volume % | Weighted $ |
|---------|------------|------------|-----------:|---------:|-----------:|
| Attendance summaries | Low | GPT-4.1 Mini | $0.002 | 35% | $0.0007 |
| Dashboard explanations | Low | GPT-4.1 Mini | $0.002 | 25% | $0.0005 |
| Attendance Q&A (Copilot) | Medium | GPT-4.1 Mini | $0.004 | 20% | $0.0008 |
| Risk prediction & intervention recommendations | High | GPT-5 | $0.020 | 15% | $0.0030 |
| Explainable AI & district benchmarking | Very High | GPT-5 | $0.030 | 5% | $0.0015 |
| **Blended Average** | — | **Hybrid** | — | **100%** | **$0.0065 / request** |

**Routing rule:** Route summaries, search, FAQs, and dashboard explanations to the triage model. Escalate only complex attendance risk analysis, intervention recommendations, and explainable AI requests to the frontier model.

**Expected cascade ratio:** **80% triage / 20% frontier**

---

## Pricing Model

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

### Decision Note

Attendance Insight delivers continuous value through attendance dashboards, reporting, and workflow management, which are covered by the platform subscription. AI-powered capabilities—including predictive risk analysis, intervention recommendations, explainable AI, and district benchmarking—are metered based on usage. This hybrid pricing model aligns revenue with the cost of delivering AI while giving districts predictable platform pricing and the flexibility to scale AI usage as adoption grows.

---

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3× | Gross margin decreases by approximately 10%. | Increase routing to lower-cost models, optimize prompts, and reserve frontier models for high-value use cases. |
| Heaviest segment doubles | Infrastructure and inference costs increase for large districts. | Introduce enterprise pricing tiers, batch processing, and volume-based licensing. |
| Model provider raises prices 50% | AI operating costs increase, reducing profitability. | Shift workloads to Anthropic, Google Gemini, or Azure OpenAI using the abstraction layer and benchmark quality before migration. |

---

## Board One-Pager

### Before (Traditional SaaS)

| Metric | Value |
|--------|------:|
| Revenue | **$45/user/month × 1 seat = $45.00** |
| COGS | **$16.00** (fixed infrastructure, storage, and support) |
| **Gross Margin** | **64%** |

---

### After (AI-Powered)

| Metric | Value |
|--------|------:|
| Revenue | **$45.00 platform fee + ($0.03 × 500 AI requests) = $60.00/user/month** |
| COGS | **$19.00** (variable AI inference + infrastructure + data + human oversight) |
| **Gross Margin** | **68%** |

---

## Net Margin Shift

| Metric | Value |
|--------|------:|
| **Δ Margin %** | **+4 percentage points** |
| **Δ Gross Profit** | **+$11.00 per user/month** |

### Narrative

Attendance Insight transitions from a traditional reporting platform to an AI-powered decision support system. While AI introduces variable inference costs, those costs are more than offset by higher recurring revenue through a platform fee plus metered AI work. The hybrid pricing model increases revenue per user from **$45 to $60 per month**, improves gross profit from **$29 to $41 per user**, and strengthens long-term net revenue retention by giving districts additional AI capabilities that expand with adoption.
