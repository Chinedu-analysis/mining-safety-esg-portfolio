# Mining Safety Analytics - ESG Portfolio

## Overview
This project analyzes workforce safety incident data from Sub-Saharan African mining operations to answer real-world ESG (Social) questions. The analysis demonstrates core skills required for ESG Analyst, HSE Data Analyst, and Sustainability Analyst roles by translating complex business questions into technical analysis with actionable insights.

---

## Business Questions

1. **Age & Experience Risk:** Are younger workers disproportionately exposed to fatal and permanently disabling incidents?
2. **Contractor Safety Equity:** Do contractors experience higher fatality density compared to direct operators across mine types?
3. **Fatal Task Analysis:** Which tasks and injury mechanisms drive the highest fatality counts?
4. **Fatigue & Shift Risk:** At what point during a shift do severe injuries peak?
5. **PPE & Life-Altering Injuries:** What percentage of amputations and fractures occur with no PPE worn?
6. **Equipment Risk Profile:** Which equipment types dominate Days Away incidents and fatalities?
7. **Artisanal vs. Formal Risk:** How do fatality mechanisms differ between artisanal and formal large mines?

---

## Analysis Approach

### 1. Age & Experience Risk
- Grouped worker ages into brackets (Under 20, 20-29, 30-39, 40-49, 50-59, 60) using Power Query
- Filtered to Fatality and Permanent Disability only
- Plotted severe injury counts against average years of experience

**📊 Visualization:**
![Age & Experience Risk](/images/chart_1_age_experience.png)

📊 **Key Findings:**
- Workers under 20 with less than 2 years of experience face the highest fatality burden
- Severe injuries decline steadily as age and experience increase
- The inverse relationship between experience and fatal outcomes is visually clear

💡 **Business Insights:**
- **Youth Safety Programs:** Target workers under 20 with enhanced supervision and task restrictions during their first two years
- **Mentorship Structures:** Pair junior workers with experienced operators during high-risk tasks
- **Portfolio-Level ESG Metric:** Track severe injury rate by age bracket as a workforce vulnerability indicator

---

### 2. Contractor Safety Equity
- Calculated Fatality Density (%): Fatalities ÷ Total Incidents × 100
- Compared Contractor vs. Operator across Artisanal, Formal Large, and Formal Small mines
- Built interactive slicer for dynamic severity filtering

**📊 Visualization:**
![Contractor Fatality Density](/images/chart_2_contractor_density.png)

📊 **Key Findings:**
- Contractor fatality density exceeds Operator density in every mine type
- The widest gap is in Formal Large mines: Contractor 79.4% vs. Operator 61.7%
- Artisanal Contractors show 72.9% fatality density — nearly 3 in 4 incidents are fatal

💡 **Business Insights:**
- **Contractor Oversight:** Audit contractor safety training, PPE compliance, and task assignment protocols
- **Supply Chain ESG:** Contractor fatality density should be a key metric in supplier risk assessments
- **Formal Doesn't Mean Safe:** Formal Large operations must extend the same safety infrastructure to contractors as direct employees

---

### 3. Fatal Task Analysis
- Built pivot table with `task_at_incident` as rows, filtered to Fatality only
- Cross-referenced with `injury_type` to identify injury profiles by task
- Analyzed "Other" category as a data quality signal

**📊 Visualizations:**
![Fatal Tasks](/images/chart_3a_fatal_tasks.png)
![Task Injury Type](/images/chart_3b_task_injury_type.png)

📊 **Key Findings:**
- "Other" leads all tasks in fatality count — a classification gap in the reporting system
- Maintenance Repair is the deadliest defined task
- Laceration, Fracture, and Contusion dominate fatal injuries across all tasks — survivable injuries with fatal outcomes

💡 **Business Insights:**
- **Classification Overhaul:** Reduce reliance on "Other" category through standardized task coding
- **Maintenance Safety:** Implement lockout/tagout, confined space, and isolation protocols for maintenance crews
- **Emergency Response Gap:** Fatalities from lacerations and fractures suggest delayed or absent trauma care — invest in on-site medical capability

---

### 4. Fatigue & Shift Risk
- Created `Hour_Range` brackets in Power Query (0-2, 2-4, 4-6, 6-8, 8-10, 10-12, 12+)
- Filtered to Fatality and Permanent Disability
- Built custom sort order to display ranges chronologically

**📊 Visualization:**
![Hours Into Shift](/images/chart_4_hours_shift.png)

📊 **Key Findings:**
- The danger zone is hours 4-8 — severe injuries peak mid-shift
- Overtime hours (8-12) show lower counts, contradicting the standard fatigue narrative
- The first two hours are the safest window

💡 **Business Insights:**
- **Mid-Shift Interventions:** Implement mandatory safety pauses, hydration breaks, or task rotations between hours 4-8
- **Rethink Fatigue Models:** Don't assume overtime is the primary risk — mid-shift complacency may be more dangerous
- **Shift Design:** Consider shorter shift structures or split shifts to avoid the 4-8 hour risk window

---

### 5. PPE & Life-Altering Injuries
- Filtered to Amputation and Fracture injury types
- Compared Hand/Finger vs. Head/Face body parts
- Calculated percentage of incidents with No PPE worn

**📊 Visualization:**
![PPE Injuries](/images/chart_5_ppe_injuries.png)

📊 **Key Findings:**
- 38.6% of life-altering Hand/Finger injuries occur with no PPE
- 41.4% of life-altering Head/Face injuries occur with no PPE
- Both body areas show similarly high non-compliance — roughly 4 in 10 critical injuries

💡 **Business Insights:**
- **PPE Enforcement:** Address the 40% non-compliance rate through spot checks and disciplinary measures
- **Glove & Hard Hat Programs:** Targeted PPE campaigns for hand and head protection specifically
- **Leading Indicator:** Track PPE compliance as a predictive metric for life-altering injury risk

---

### 6. Equipment Risk Profile
- Compared Days Away density and Fatality density by equipment type
- Built treemap for fatality distribution visualization
- Calculated outcome profiles to identify equipment with no "minor" failure mode

**📊 Visualizations:**
![Equipment Treemap](/images/chart_6a_equipment_treemap.png)
![Equipment Density](/images/chart_6b_equipment_density.png)

📊 **Key Findings:**
- Mobile Equipment dominates both outcomes: 33.5% of fatalities, 32.5% of days away
- "None" (no equipment involved) is second at 15.4% — pointing to ground control and environmental failures
- For nearly every equipment type, fatality and days away densities are nearly equal — there are no "minor" incidents

💡 **Business Insights:**
- **Mobile Equipment Priority:** Invest in collision avoidance, proximity detection, and remote operation
- **Ground Control:** The "None" category fatalities likely represent pit collapses and falls of ground — geotechnical assessments needed
- **No Minor Incidents:** Every equipment interaction is potentially life-threatening — engineering controls over administrative controls

---

### 7. Artisanal vs. Formal Risk Profiles
- Filtered to Fatality only, split by Artisanal and Formal Large mine types
- Compared top injury mechanisms side by side
- Tested hypothesis that ground failure dominates artisanal risk while machinery dominates formal risk

**📊 Visualization:**
![Mine Type Comparison](/images/chart_7_mine_type_comparison.png)

📊 **Key Findings:**
- Pit Collapse is the #2 killer in Artisanal mines — completely absent in Formal Large
- Struck By Object and Hit By Moving lead in Formal Large operations
- "Other" is #1 in both — the classification blind spot persists across mine types

💡 **Business Insights:**
- **Artisanal Ground Control:** Basic geotechnical training, timber supports, and slope monitoring could significantly reduce Pit Collapse fatalities
- **Formal Traffic Management:** Collision avoidance systems, vehicle-pedestrian segregation, and proximity detection for Formal Large sites
- **Different Risks, Different Solutions:** Artisanal and Formal mines require entirely different safety investment strategies — one size does not fit all

---

## Cross-Cutting Observation

The **"Other"** category dominates across multiple analyses — tasks, injury mechanisms, and mine type breakdowns. This recurring finding indicates a systemic gap in the incident classification system. Fatalities are occurring in undefined categories, masking root causes and delaying targeted interventions. Fixing the classification system is a prerequisite to fixing the safety outcomes.

---

## Strategic Recommendations

### Workforce Protection
- **Youth Safety Programs:** Target workers under 20 with enhanced supervision and task restrictions during their first two years
- **Contractor Standards:** Audit contractor safety training and PPE compliance, especially in Formal Large operations
- **PPE Enforcement:** Address the 40% non-compliance rate for hand and head protection during high-risk tasks

### Operational Controls
- **Mid-Shift Interventions:** Implement mandatory safety pauses or shift rotations during hours 4-8
- **Maintenance Safety:** Strengthen lockout/tagout, isolation procedures, and confined space protocols

### Equipment & Engineering
- **Mobile Equipment Priority:** Invest in collision avoidance, proximity detection, and remote operation
- **Ground Control in Artisanal Mines:** Basic geotechnical training and support structures for Pit Collapse prevention

### Data Systems
- **Fix the "Other" Problem:** Overhaul incident classification to reduce reliance on catch-all categories
- **Contractor Incident Tracking:** Separate contractor safety metrics in ESG reporting

---

## Technical Details

| Category | Details |
| :--- | :--- |
| Analysis Tool | Microsoft Excel |
| Data Transformation | Power Query (custom columns, conditional logic) |
| Visualization | Pivot Charts, Combo Charts, Treemap, Slicers |
| Key Metrics | Fatality Density (%), Days Away Density (%) |
| Data Source | `safety_incidents.csv` — mining incident records from Sub-Saharan Africa |
| Records Analyzed | 1,300+ incidents |

---

## Methodology Note

Fatality Density (%) is calculated as: `(Fatalities ÷ Total Incidents) × 100` and is used as a proxy metric where hours-worked data is unavailable for a full TRIR (Total Recordable Incident Rate) calculation. This allows for meaningful comparison across employment types and mine categories without workforce headcount data.

Data transformation was performed using Power Query custom columns to create age brackets, hour ranges, and sort order fields. Analysis was conducted using pivot tables with interactive slicers for dynamic severity-level filtering.

---

## Appropriate Use

This project is intended for:
- Development and benchmarking of injury prediction models
- Educational demonstrations of occupational health analytics
- Methodological research on causal inference in safety data
- Testing data pipelines and visualization tools

This project is **not** intended for:
- Making actual safety policy decisions without validation
- Replacing real incident reporting systems
- Insurance risk assessment of real operations
- Legal proceedings or compliance audits

---

*Built with Microsoft Excel and Power Query. All findings are based on provided incident data and should not be interpreted as operational safety recommendations without independent validation.*

