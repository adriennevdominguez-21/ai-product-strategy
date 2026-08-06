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
| Accuracy | 90% | Weekly evaluation using a dataset of 300 golden test cases (including adversarial examples), scored with rule-based validation and LLM-as-a-judge. Ship only if overall accuracy is ≥90% and no critical safety tests fail. | <85% → trigger gold-set audit |
| Hallucination rate | <1% | eekly evaluation on 300 golden test cases using Rule + LLM-as-a-judge to identify unsupported or fabricated claims. | >3% → auto-rollback to last good model |
| Latency (p95) | <2s | Monitor median response time weekly across production requests. | > 5s → page on-call |
| Drift velocity | <0.5%/4w | Weekly monitoring of production data against the training dataset using drift detection metrics. | >2%/4w → trigger gold-set audit |

## HITL Architecture

**Trigger:** Human review is triggered for predictions with confidence below 60% or any high-impact student intervention recommendation.

**Reviewer:** The school's attendance coordinator or counselor, with district administrators reviewing school-level trends and recommendations.

**Feedback loop:** Reviewer corrections are added to the gold set and used during future evaluations and model retraining.


## Red-Team Findings
*What failure mode did your partner find that you missed?*
My partner found that Attendance Insight could treat excused and unexcused absences the same, causing students with legitimate medical, disability-related, or approved absences to be incorrectly classified as high risk. Our original golden dataset missed this failure because it tested absence counts without including absence type or accommodation context.
