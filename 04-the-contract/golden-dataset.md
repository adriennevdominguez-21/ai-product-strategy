# Golden Dataset & Reliability Contract

## Golden Dataset Spec

## Test Cases

### 1. High-Risk Student

- **Edge Case:** No
- **Judge:** Rule + LLM

**Input**

> Student has **12 absences**, attendance declined from **96% to 82%** over 6 weeks, declining grades, and no prior interventions.

**Expected Output**

> High attendance risk. Recommend immediate outreach, parent conference, an attendance improvement plan, and counselor referral. Explain the factors contributing to the prediction.

---

### 2. Improving Student

- **Edge Case:** No
- **Judge:** Rule + LLM

**Input**

> Student has **4 absences**, attendance is improving, grades remain above 90%, and previous family outreach was successful.

**Expected Output**

> Low attendance risk. Recommend continued monitoring only and avoid unnecessary intervention.

---

### 3. School-Level Trend

- **Edge Case:** No
- **Judge:** Rule + LLM

**Input**

> School's chronic absenteeism rate increased from **18% to 24%** compared to last semester.

**Expected Output**

> Flag a school-level attendance concern, identify key trends, and recommend targeted interventions for high-risk student groups.

---

### 4. Limited Historical Data

- **Edge Case:** Yes
- **Judge:** Rule + LLM

**Input**

> Student transferred into the district last week with only **three days of attendance history**.

**Expected Output**

> Indicate there is insufficient data for a reliable prediction. Recommend monitoring until additional attendance history is available.

---

### 5. Conflicting Data

- **Edge Case:** Yes
- **Judge:** Rule

**Input**

> Attendance records contain conflicting duplicate entries from two source systems.

**Expected Output**

> Detect the data quality issue, avoid generating a confidence score, and recommend data validation before any intervention.

---

## Dataset Health

| Metric | Value |
|---------|------:|
| **Total Test Cases** | **5** |
| **Edge Cases** | **2 (40%)** |
| **Rule Only** | **20%** |
| **LLM Only** | **0%** |
| **Rule + LLM** | **80%** |


**Adversarial rows included:** 2

**Coverage gaps identified by partner:**
- Students with excused vs. unexcused absences.
- Seasonal attendance patterns (e.g., flu outbreaks, weather closures).
- Students receiving special education or Section 504 accommodations.
- English learner and multilingual family communication scenarios.
- Bias evaluation across demographic groups.
- Missing or delayed SIS data feeds.
- Multiple interventions with conflicting outcomes.
- District policy differences for chronic absenteeism thresholds.
- False positives where attendance improves without intervention.
- Confidence calibration for low-data or ambiguous cases.

## Confidence UX Design

## Confidence UX Design

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


## Reliability Contract

| Metric | Target | Measurement | Alert Threshold |
|--------|--------|-------------|-----------------|
| Accuracy | | | |
| Hallucination rate | | | |
| Latency (p95) | | | |
| Drift velocity | | | |

## HITL Architecture
<!-- When does a human step in? What's the escalation path? -->

## Red-Team Findings
*What failure mode did your partner find that you missed?*
