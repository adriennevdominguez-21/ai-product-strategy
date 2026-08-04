# Compounding System Design
## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Educator acceptance, modification, or rejection of AI recommendations; intervention selections; intervention outcomes; attendance improvements; corrected risk classifications; and reviewer feedback | Better risk predictions, more relevant intervention recommendations, improved confidence calibration, expanded golden-dataset coverage, and stronger personalization to district workflows. | Y | active |
| Cross-Domain Transfer | Attendance history combined with grades, behavior incidents, enrollment data, demographics, intervention history, school-level trends, and district attendance policies. | More contextual risk assessments, identification of relationships across student outcomes, improved recommendations across schools and grade levels, and earlier detection of emerging attendance risks. | Y | active |
| Network Intelligence | Privacy-preserving and anonymized attendance patterns, intervention outcomes, benchmarks, and educator feedback contributed by multiple districts. | anonymized attendance patterns, intervention outcomes, benchmarks, and educator feedback contributed by multiple districts.Cross-district benchmarks, broader pattern recognition, identification of effective interventions across comparable student populations, and improved predictions for every participating district. | Y | broken |

**Broken loop identified by partner:** ·
**Fix plan:** ·

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

**How knowledge flows:** Educators provide feedback by reviewing AI predictions, modifying recommendations, recording interventions, and documenting student outcomes. Attendance Insight combines this knowledge with attendance, academic, behavioral, enrollment, and district-policy data to improve predictions and share effective practices across schools and teams. Knowledge currently flows well within districts, but privacy constraints limit cross-district learning until federated learning or anonymized benchmarking is implemented.

**Where it silos:** Knowledge is especially siloed across districts because student privacy and FERPA requirements restrict sharing identifiable data and outcomes. This prevents Attendance Insight from fully learning which interventions work across broader populations.


<!-- Governance Policy, Attendance Insight -->

## Governance Policy

**Scope:** AI features within Attendance Insight, including attendance-risk predictions, intervention recommendations, confidence scores, explanations, prioritized alerts, automated summaries, and the conversational attendance assistant. It also covers educator review, corrections, feedback collection, model evaluation, and the use of student data to produce these outputs. Excludes: Traditional attendance reporting, non-AI workflow tools, internal-only analytics dashboards, SIS data-entry processes, and final disciplinary or legal decisions. These areas are governed by separate district data, security, student-discipline, and FERPA policies.

**Autonomy boundaries:** Generate summaries, detect attendance trends, prioritize dashboard alerts, calculate risk indicators, and recommend possible interventions., auto. Contact families, assign interventions, create attendance improvement plans, refer students to counselors, or update official student records—even when AI confidence is high., human approval required. Make disciplinary decisions, determine truancy or legal action, change enrollment status, deny student services, or make decisions based solely on protected characteristics., never auto.

**Escalation triggers:** 1. AI confidence is below 60%. 2. Source data contains missing, conflicting, duplicate, or delayed records. 3. The recommendation involves family contact, counselor referral, an attendance improvement plan, or an official-record change. 4. The recommendation could lead to disciplinary, truancy, enrollment, or legal action. 5. The case involves special education, Section 504, language-access, or accommodation requirements.

**Audit cadence:** Weekly, AI confidence is below 60%. Source data contains missing, conflicting, duplicate, or delayed records. The recommendation involves family contact, counselor referral, an attendance improvement plan, or an official-record change. The recommendation could lead to disciplinary, truancy, enrollment, or legal action. The case involves special education, Section 504, language-access, or accommodation requirements. (AI product and engineering teams). Monthly, Human overrides, rejected recommendations, intervention outcomes, and data-quality issues (Product owner, attendance coordinators, and data team). Quarterly, Bias across demographic groups, confidence calibration, policy compliance, and model drift (Governance committee and district administrators). Quarterly, Overall student impact, FERPA compliance, vendor risk, security controls, and whether the AI should continue operating (District leadership, Legal).

**Regulatory exposure (EU AI Act / other):** FERPA, COPPA, State student-privacy laws, Title VI and Title IX, Section 504, ADA, and IDEA. Risk tier: high. Controls: Attendance Insight uses role-based access, encryption, audit logs, data minimization, retention limits, vendor controls, and FERPA-compliant handling of student records. It also requires human approval for consequential decisions, monitors accuracy and demographic performance, supports corrections and appeals, and prohibits fully automated disciplinary, legal, enrollment, or accommodation decisions..

## Agent Topology

_Not shipping agents this version._


## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |

**Total tools found:**
**Tools after triage:**
**Estimated hidden spend:**
