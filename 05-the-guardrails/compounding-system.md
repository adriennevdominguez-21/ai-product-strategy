# Compounding System Design
## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Educator acceptance, modification, or rejection of AI recommendations; intervention selections; intervention outcomes; attendance improvements; corrected risk classifications; and reviewer feedback | Better risk predictions, more relevant intervention recommendations, improved confidence calibration, expanded golden-dataset coverage, and stronger personalization to district workflows. | Y | active |
| Cross-Domain Transfer | Attendance history combined with grades, behavior incidents, enrollment data, demographics, intervention history, school-level trends, and district attendance policies. | More contextual risk assessments, identification of relationships across student outcomes, improved recommendations across schools and grade levels, and earlier detection of emerging attendance risks. | Y | active |
| Network Intelligence | Privacy-preserving and anonymized attendance patterns, intervention outcomes, benchmarks, and educator feedback contributed by multiple districts. | Cross-district benchmarks, broader pattern recognition, identification of effective interventions across comparable student populations, and improved predictions for participating districts. | Y | Broken |

**Broken loop identified by partner:** Network intelligence—attendance patterns and intervention outcomes are collected across districts but are not fed into a centralized, privacy-preserving intelligence layer.

**Fix plan:** Develop FERPA-compliant federated learning and anonymized benchmarking so cross-district outcomes can improve predictions and intervention recommendations without exposing identifiable student data.

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

**How knowledge flows:** Educators provide feedback by reviewing AI predictions, modifying recommendations, recording interventions, and documenting student outcomes. Attendance Insight combines this knowledge with attendance, academic, behavioral, enrollment, and district-policy data to improve predictions and share effective practices across schools and teams. Knowledge currently flows well within districts, but privacy constraints limit cross-district learning until federated learning or anonymized benchmarking is implemented.

**Where it silos:** Knowledge is especially siloed across districts because student privacy and FERPA requirements restrict sharing identifiable data and outcomes. This prevents Attendance Insight from fully learning which interventions work across broader populations.


<!-- Governance Policy, Attendance Insight -->

## Governance Policy

**Scope:** AI features within Attendance Insight, including attendance-risk predictions, intervention recommendations, confidence scores, explanations, prioritized alerts, automated summaries, and the conversational attendance assistant. It also covers educator review, corrections, feedback collection, model evaluation, and the use of student data to produce these outputs. Excludes: Traditional attendance reporting, non-AI workflow tools, internal-only analytics dashboards, SIS data-entry processes, and final disciplinary or legal decisions. These areas are governed by separate district data, security, student-discipline, and FERPA policies.

**Autonomy Boundaries:**

| Level | Decisions | Decision-Maker |
|---|---|---|
| 🟢 Auto | Generate summaries, detect attendance trends, prioritize dashboard alerts, calculate risk indicators, and recommend possible interventions. | AI, with outputs logged and visible to authorized educators. |
| 🟡 Human Approval | Contact families, assign interventions, create attendance improvement plans, refer students to counselors, or update official student records—even when AI confidence is high. | Authorized educator, attendance coordinator, counselor, or district administrator. |
| 🔴 Never Auto | Make disciplinary decisions, determine truancy or legal action, change enrollment status, deny services or accommodations, or act solely on protected characteristics. | Authorized school or district personnel following applicable policy and law. |

**Escalation triggers:** 
1. AI confidence is below 60%. 
2. Source data contains missing, conflicting, duplicate, or delayed records. 
3. The recommendation involves family contact, counselor referral, an attendance improvement plan, or an official-record change. 
4. The recommendation could lead to disciplinary, truancy, enrollment, or legal action. 
5. The case involves special education, Section 504, language-access, or accommodation requirements.


**Audit Cadence:**

| Frequency | What We Review | Who Reviews It |
|---|---|---|
| Weekly | Accuracy, hallucination rate, p95 latency, drift, failed safety tests, escalated cases, and data-quality failures. | AI product, engineering, and evaluation teams |
| Monthly | Human overrides, rejected recommendations, intervention outcomes, user feedback, and recurring data-quality issues. | Product owner, attendance coordinators, and data team |
| Quarterly | Demographic performance, confidence calibration, policy compliance, model changes, vendor risk, and Shadow AI usage. | AI governance committee, district administrators, privacy, and legal teams |
| Annually | Student impact, FERPA compliance, security controls, retention practices, vendor agreements, and whether the AI should continue operating. | District leadership, privacy officer, legal counsel, and an independent reviewer where required |

**Regulatory exposure (EU AI Act / other):** FERPA, COPPA, State student-privacy laws, Title VI and Title IX, Section 504, ADA, and IDEA. Risk tier: high. Controls: Attendance Insight uses role-based access, encryption, audit logs, data minimization, retention limits, vendor controls, and FERPA-compliant handling of student records. It also requires human approval for consequential decisions, monitors accuracy and demographic performance, supports corrections and appeals, and prohibits fully automated disciplinary, legal, enrollment, or accommodation decisions.

## Agent Topology

_Not shipping agents this version._


## Shadow AI Audit

| Workaround | Signal Source | Signal Type | Frequency | Spend ($/mo) | Decision |
|---|---|---|---|---:|---|
| Exporting attendance data into general-purpose AI tools to create student and school summaries | User interview | Capability gap | H | $100/mo | Build |
| Using Zapier or Make to send risk alerts and intervention reminders through email or team messaging | Zapier/Make | Workflow gap | H | $100/mo | Partner |
| Building custom dashboards and risk models through the Attendance Insight API | API pattern | Capability gap | M | $1,000/mo | Build |
| Using external translation AI to draft multilingual family outreach | Support ticket | Capability gap | M | $200/mo | Partner |
| Creating independent chatbots that answer general attendance-policy questions | Sales call | Pricing gap | L | $100/mo | Ignore |

## Pattern Assessment
- Workarounds found: 5
- Build candidates: 2
- Partner candidates: 2
- Ignore decisions: 1
- Adjacent spend: $1500/mo
- Dominant signal: Capability gap

## Action Plan
### Build
Attendance Insight should absorb secure AI-generated attendance summaries, configurable dashboards and risk models, and automated risk alerts and intervention reminders directly into the product. These are frequent, core workflow needs involving sensitive student data, so native capabilities provide stronger FERPA controls, consistent quality, and a better user experience than external workarounds.

### Partner
Attendance Insight should officially integrate with approved workflow-automation tools such as Zapier for sending alerts and intervention reminders through district-authorized communication channels. It should also integrate with a vetted, education-focused translation provider for multilingual family outreach, with human review required before messages are sent.

### Ignore + Monitor
Attendance Insight can allow users to continue using external tools for general attendance-policy research, presentation creation, and analysis of fully anonymized, non-student-specific data. Users should not export identifiable student records, intervention notes, or sensitive accommodation information to unapproved AI tools.

## Roadmap Brief
Based on your audit: 5 user-side workarounds discovered.
Decisions: 2 build · 2 partner · 1 ignore · 0 TBD.
Estimated adjacent spend: $1500/mo across surveyed users.
Dominant signal: Capability gap.

Recommended next step: Capability gaps dominate, users want something your product does not do. Strongest near-term move is building one or two of these natively before a competitor does.

Sequence the Build column by frequency × strategic relevance. Confirm Partner candidates with the external tools' partnership teams. Re-run this audit each quarter, workarounds shift fast.

