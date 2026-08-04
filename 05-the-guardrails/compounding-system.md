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



## Governance Policy

**Scope:**
**Autonomy boundaries:**
**Escalation triggers:**
**Audit cadence:**
**Regulatory exposure (EU AI Act / other):**

## Agent Topology
<!-- If using agents: what can each agent do? What can't it do? Who approves what? -->

## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |

**Total tools found:**
**Tools after triage:**
**Estimated hidden spend:**
