# Flare Risk Rules

This document describes the conceptual rule-based logic used to estimate endometriosis flare risk from symptom, sleep, and wearable-related features. These rules are not clinical guidelines but are informed by patterns described in the literature and clinical reasoning.

---

## 1. Inputs to Flare Risk

Key inputs include:

- Daily pain score (0–10)  
- Severe pain flag (pain ≥ 7)  
- Sleep duration and quality (from sleep dataset)  
- Wrist temperature deviation from baseline  
- Mood and fatigue scores  
- Cycle phase (from hormonal/self-report data)  

These inputs are combined into intermediate signals and a final flare risk score.

---

## 2. Core Rule Components

### Severe Pain Rule
- If `pain_score >= 7` for at least 3 consecutive days, mark as:
  - `sustained_severe_pain = 1`

### Sleep Disruption Rule
- If `sleep_hours < 5` or `sleep_quality` is below a defined threshold for 2 or more days in a 3-day window:
  - `sleep_disruption_flag = 1`

### Temperature Deviation Rule
- If wrist temperature is above a set deviation from baseline (for example, > 0.5–1.0 degrees over a 7-day baseline):
  - `temp_elevated_flag = 1`

### Phase-Adjusted Sensitivity
- During specific phases (for example, late luteal or menstrual), thresholds may be relaxed or weighted differently to reflect higher baseline symptom risk.

---

## 3. Composite Flare Risk Index

A simplified conceptual flare risk index might be defined as:

- Start with `flare_risk_score = 0`  
- Add points for each condition:

  - +2 if `sustained_severe_pain = 1`  
  - +1 if `sleep_disruption_flag = 1`  
  - +1 if `temp_elevated_flag = 1`  
  - +1 if high fatigue or low mood are present  
  - Optional: adjust by cycle phase weighting  

Example interpretation:

- 0–1: Low flare risk  
- 2–3: Moderate flare risk  
- 4 or more: High flare risk  

These thresholds are conceptual and customizable.

---

## 4. Alerts and Outputs

Based on the flare risk score:

- Low risk: Continue monitoring and self-management  
- Moderate risk: Notify user of potential flare patterns and suggest tracking more closely  
- High risk: Suggest documenting symptoms for a clinician visit and provide a structured summary  

For clinicians, the system could generate a monthly report summarizing:

- Number of high-risk days  
- Relationship between flares and cycle phases  
- Co-occurrence of pain, sleep changes, and temperature deviations  

---

## 5. Future Refinement

Future iterations could:

- Use machine learning models (e.g., logistic regression, random forests) trained on labeled flare events  
- Tune rule thresholds based on real-world outcomes  
- Incorporate additional biomarkers (for example, HRV directly, if available as a time series)  

The current rules serve as an interpretable starting point for flare detection logic in a digital health context.
