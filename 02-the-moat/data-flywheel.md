# Data Flywheel Map

> Score each loop 1-5. Your weakest loop is where competitors attack first.
> The four loops below are the M2 starting point - adapt if your product has 2 or 6 loops instead of 4.

## Flywheel Loops

| Loop | What It Measures | Score 1 | Score 5 | Score |
|------|------------------|---------|---------|-------|
| **Correction** | Do users fix AI outputs? Is that signal captured and reused? | No capture | Automated retraining | 4/5 |
| **Preference** | Does the product learn individual / team preferences over time? | Stateless | Deep personalization | 4/5 |
| **Domain Context** | Does usage in one area improve quality in adjacent areas? | Siloed | Cross-domain transfer | 5/5 |
| **Network** | Does each new user / team make the product better for everyone? | Isolated | Strong network effects | 3/5 |

### Correction Loop - 4/5
**What you capture today:** 
User actions such as accepted, modified, or rejected AI recommendations, intervention outcomes, attendance improvements, and educator feedback on prediction accuracy.

**How it compounds:** 
Each interaction creates labeled feedback that improves future risk models, personalizes recommendations, increases educator trust, and makes the AI more accurate over time.

### Preference Loop - 4/5
**What you capture today:**
User preferences such as preferred intervention strategies, dashboard views, alert settings, and how individual educators respond to AI recommendations.

**How it compounds:**
As educators use the platform, the AI personalizes recommendations and prioritizes alerts based on each user's behavior and each school's intervention practices, increasing relevance and adoption.

### Domain Context Loop - 5/5
**What you capture today:**
Relationships between attendance, grades, behavior incidents, demographics, intervention history, and school-level trends across the district.

**How it compounds:**
Insights learned from one school, grade level, or student population improve predictions and recommendations across similar contexts, making the AI increasingly effective as it learns district-wide patterns.

### Network Loop - 3/5
**What you capture today:**
Anonymized intervention outcomes, attendance trends, and educator feedback from multiple schools and districts.

**How it compounds:**
As more districts contribute data, the AI identifies broader attendance patterns and more effective intervention strategies, though privacy requirements and district-specific policies limit how much knowledge can be shared across organizations.

### Total Flywheel Score
**16/20**

### Weakest Loop
**Network Loop (3/5)**

### Fix for Weakest Loop
Develop a privacy-preserving federated learning or benchmarking capability that allows districts to contribute anonymized outcomes and best practices, enabling the AI to learn from cross-district patterns without exposing sensitive student data.

---

## Encroachment Threat Assessment

### 1. Platform Encroachment
**Attacker:** PowerSchool

**Vector:** Integrates AI-powered attendance risk prediction, intervention recommendations, and district analytics directly into its existing Student Information System, eliminating the need for a standalone solution.

**Time-to-threat:** 12–24 months

**% of value at risk:** 70%

### 2. Vertical Competitor
**Attacker:** EveryDay Labs

**Vector:** Expands its attendance intervention platform with more advanced predictive AI, personalized outreach, and evidence-based intervention recommendations focused exclusively on reducing chronic absenteeism.

**Time-to-threat:** 6–12 months

**% of value at risk:** 50%

### 3. Adjacent Expansion
**Attacker:** Frontline Education

**Vector:** Adds AI-driven attendance insights and intervention recommendations to its student management, analytics, and administrative workflow products, leveraging existing district relationships to drive adoption.

**Time-to-threat:** 12–18 months

**% of value at risk:** 40%

---

## 90-Day Encroachment Plan

*Your partner played the Big Tech attacker. What was their plan to kill you?*

**Attacker:** PowerSchool

**Attack vector (target the weakest loop):** Launch a privacy-preserving, federated AI model that learns from anonymized attendance patterns across participating districts without exposing student data, turning Attendance Insight's siloed data into PowerSchool's competitive advantage.

**Weeks 1-4 - what they ship:** Release AI-powered attendance risk prediction, intervention recommendations, and district benchmarking trained on anonymized data from thousands of schools while ensuring no student-level data leaves a district.

**Weeks 5-8 - how they poach users:** Offer the new AI capabilities at no additional cost to existing PowerSchool customers, emphasizing that districts benefit from insights learned across the network while maintaining FERPA compliance and data privacy.

**Weeks 9-12 - why users don't come back:** Districts begin receiving more accurate predictions and stronger intervention recommendations because the AI continuously learns from cross-district outcomes, making Attendance Insight's siloed models appear less effective over time.

**Your defense:** Build a privacy-preserving federated learning network that allows districts to securely contribute anonymized outcomes, while differentiating through explainable AI, configurable intervention workflows, and district-specific policy intelligence that delivers both network-wide and local insights.
