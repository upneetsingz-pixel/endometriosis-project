# Feature Engineering

This document describes how raw symptom, wearable, and lifestyle data can be transformed into meaningful features for flare risk detection and endometriosis management.

---

## 1. Symptom Features

From `structured_endometriosis_data.csv` and self-report inputs:

- Pain score (0–10)  
- Binary indicators for severe pain (e.g., pain ≥ 7)  
- GI symptom flags (bloating, nausea, constipation/diarrhea)  
- Mood and fatigue scores  
- Daily overall symptom severity index  

Example engineered features:
- `severe_pain_flag`  
- `gi_symptom_presence`  
- `high_fatigue_flag`  

These features represent daily clinical burden.

---

## 2. Sleep and Lifestyle Features

From `Sleep_health_and_lifestyle_dataset.csv`:

- Hours of sleep per night  
- Sleep quality scores  
- Rolling averages:
  - 3-day average sleep duration  
  - 7-day average sleep duration  
- Binary features for:
  - Short sleep (e.g., < 5 hours)  
  - Poor sleep quality  

Lifestyle-related:
- Physical activity level  
- Caffeine and alcohol intake  
- Stress level scores  

These features help model how sleep and lifestyle interact with symptom severity.

---

## 3. Wrist Temperature Features

From `wrist_temperature.csv`:

- Daily wrist temperature values  
- Deviations from personal baseline (e.g., delta from 7-day mean)  
- Temperature variability over a rolling window  

Possible engineered features:
- `temp_delta_from_baseline`  
- `high_temp_flag`  
- `temp_variability_index`  

These can serve as proxies for hormonal shifts, inflammation, or cycle phase.

---

## 4. Fitness and Exercise Features

From `demographic_vo2_max.csv` and `exercise.csv`:

- VO2 max as a fitness indicator  
- Exercise frequency per week  
- Average exercise duration and intensity  

Engineered variables:
- `active_days_per_week`  
- `high_intensity_exercise_flag`  

These features help interpret HRV and fatigue in context (for example, low HRV may be less concerning in the context of very intense training).

---

## 5. Hormonal and Cycle-Phase Features

From `hormones_and_selfreport.csv`:

- Cycle day or phase (e.g., follicular, ovulatory, luteal, menstrual)  
- Self-reported hormonal symptoms  

Engineered features:
- One-hot encoded cycle phases  
- Phase-specific symptom averages  
- Phase-aligned pain and mood patterns  

These features are crucial for aligning symptoms and flares with menstrual cycle dynamics.

---

## 6. Combined Multi-Modal Features

Key multi-modal engineered features may include:

- Pain and sleep interaction (e.g., severe pain + short sleep)  
- Pain and HRV interaction (if HRV is derived or available)  
- Temperature and symptom co-occurrence  
- Composite flare risk index combining:
  - severe pain  
  - sleep disruption  
  - temperature deviation  
  - stress or mood indicators  

These combined features are used in rule-based logic and in exploratory clustering to identify symptom phenotypes.

---

## Summary

The feature engineering strategy focuses on:
- Converting raw signals into clinically interpretable variables  
- Using rolling windows to smooth noisy data  
- Aligning features with menstrual cycle phases  
- Combining symptoms and wearables to better capture flare dynamics

These features can then be used in rule-based systems, clustering, or future machine learning models.
