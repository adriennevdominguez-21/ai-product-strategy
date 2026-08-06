# Three-Horizon Roadmap & Board Pitch

## Roadmap

### Horizon 1 — Now (0-3 months)
*Quick wins. Ship with existing capabilities.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Detect students at risk of chronic absenteeism | ≥90% golden-set accuracy with no critical safety failures | M |
| Explain each risk classification and communicate uncertainty | ≥80% of educators report that risk drivers and confidence are understandable | H |
| Distinguish excused, medical, disability-related, and unexcused absences | 100% of absence-type safety tests pass | H |
| Block predictions based on missing, duplicate, delayed, or conflicting data | 100% of known data-quality conflicts trigger human review | H |
| Require human approval for consequential student actions | 100% of high-impact interventions receive documented human approval | H |
| Expand the golden dataset and implement reliability monitoring | 300 representative test cases; weekly monitoring of accuracy, hallucination, latency, drift, overrides, and fairness | H |
| Validate intervention recommendations and configurable risk alerts | ≥60% recommendation acceptance or modification rate; ≥40% of alerts lead to review or action | M |

### Horizon 2 — Next (3-9 months)
*Bets. Requires new capabilities or integrations.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Track intervention completion and attendance outcomes | ≥80% of assigned interventions have a recorded outcome | M |
| Use educator corrections and intervention outcomes for recursive learning | Measurable model improvement across two consecutive evaluation cycles | M |
| Build configurable district policy and intervention workflows | Launch with at least three district policy configurations and ≥70% administrator satisfaction | M |
| Integrate multilingual family outreach through an approved translation partner | ≥95% translation approval rate after educator review with no unauthorized automatic sends | M |
| Validate hybrid AI Premium pricing with district buyers | At least three pilot districts accept pricing or provide documented willingness-to-pay evidence | M |

### Horizon 3 — Bet (9-18 months)
*Moonshots. High uncertainty, high potential.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Launch privacy-preserving cross-district benchmarking and federated learning | At least five districts participate with no identifiable student data leaving district boundaries | L |
| Optimize interventions using anonymized cross-district outcomes | Demonstrate a statistically meaningful improvement in recommendation effectiveness over district-only models | L |

## Board Pitch
**Thesis (1 sentence):**
Attendance Insight helps K–12 leaders identify attendance risk earlier and take more effective, accountable action before students become chronically absent.

**The case:**
1. Why now: The prototype is complete enough to test with districts, but our advantage window is limited: PowerSchool could bundle comparable attendance predictions and recommendations into its existing platform within 12–24 months. We need fall pilots to determine whether Attendance Insight produces better decisions and outcomes before committing to broader scale.
2. What's defensible: The defensible asset is not the prediction alone; it is the combination of district-specific attendance policies, embedded intervention workflows, educator corrections, and longitudinal intervention outcomes. Those signals can improve recommendations within each district, while cross-district benchmarking remains an unproven future advantage rather than a moat we can claim today.
3. The economics: At the expected usage level, the model produces $60 in monthly revenue per user against $19 in COGS, increasing projected gross margin from 64% to 68% and gross profit by $11 per user per month. Those economics depend on unvalidated usage and willingness-to-pay assumptions, so the first three district pilots must test pricing and 10x-usage sensitivity before we scale.

**The risks:**
1. Trust / failure modes: The unacceptable failure is incorrectly labeling a student as high risk because the system treats an excused, medical, or disability-related absence like an unexcused absence, leading to an inappropriate intervention. We mitigate that with absence-specific safety tests, visible confidence, blocked scoring when data conflicts, mandatory human approval for consequential actions, and a 300-case evaluation set that must reach at least 90% accuracy with no critical safety failures before release.
2. Scale / governance: At 10x usage, inference costs, data-quality failures, human-review volume, model drift, and privacy exposure all increase; the cross-district learning loop is also currently broken. We will control scale through lower-cost routing for routine work, explicit escalation triggers, role-based access, weekly reliability reviews, quarterly governance audits, and no autonomous disciplinary, legal, enrollment, or accommodation decisions.
3. Competitive: The forcing scenario is PowerSchool offering comparable capabilities at no additional cost while learning from a larger district network. If our pilots do not demonstrate more accurate risk identification, meaningful educator adoption, improved intervention completion, measurable attendance impact, and willingness to pay, we stop expansion rather than fund a feature an incumbent can bundle.

**The ask:**
Approve $1.8 million and eight dedicated employees for 12 months, with a 90-day release gate, to complete the reliability foundation, integrate district data, and run pilots with two to three districts. The team will include one product manager, two ML engineers or data scientists, two full-stack engineers, one data-integration engineer, one MLOps and security engineer, and one education implementation and research lead. Funding this means pausing native multilingual outreach and other non-core chatbot or custom-dashboard work, using partners where necessary, and withholding investment in federated learning until the pilots validate outcomes and demand.


## M1 Baseline vs. Now
*Your 3-sentence AI strategy from Module 1 vs. what you'd say now:*

**M1 baseline:** Attendance Insight is an AI-powered decision-support platform that helps educators identify attendance risks earlier and recommend timely interventions. It analyzes attendance and related student data to predict risk, identify trends, and improve educator decision-making. We would stop investing if the AI fails to improve risk identification, attendance outcomes, or user trust and adoption.

**Now:** Attendance Insight is a high-governance attendance intelligence platform that combines explainable predictions, district-specific policy context, and human-approved interventions to improve measurable student outcomes. Our near-term priority is proving the bet through a controlled district pilot, a 300-case golden dataset, and explicit reliability, fairness, adoption, and outcome thresholds. If validated, intervention outcomes and privacy-preserving cross-district learning will create a defensible data flywheel while hybrid pricing supports sustainable AI economics.
