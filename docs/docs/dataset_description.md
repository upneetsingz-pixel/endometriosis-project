# Dataset Description

This project uses several datasets to simulate a multi-modal digital health environment for detecting and managing endometriosis. The datasets include symptom reports, wearable metrics, lifestyle data, and physiological indicators. Each dataset serves a specific analytical purpose.

---

## 1. structured_endometriosis_data.csv
**Purpose:**  
Core symptom dataset used to understand pain levels, menstrual cycle phases, mood changes, and daily self-reported patterns.

**Typical variables include:**  
- Pain scores  
- Bloating, GI symptoms  
- Mood and fatigue  
- Menstrual cycle phase  
- Daily severity ratings  
- Self-reported triggers  

---

## 2. Sleep_health_and_lifestyle_dataset.csv
**Purpose:**  
Provides sleep and lifestyle context, which is important for flare prediction and stress-related triggers.

**Variables include:**  
- Hours of sleep  
- Sleep quality  
- Physical activity  
- Alcohol/caffeine intake  
- Stress indicators  

This dataset helps validate relationships between sleep disruption and endometriosis symptom flare-ups.

---

## 3. wrist_temperature.csv
**Purpose:**  
Simulated wrist-temperature time series used to explore hormonal or inflammation-related deviations.

**Typical variables:**  
- Daily wrist temperature (morning/evening)  
- Temperature deltas  
- Trend over time  

Wrist temperature is sometimes used as a proxy for ovulation, inflammation, or metabolic change.

---

## 4. demographic_vo2_max.csv
**Purpose:**  
Provides baseline fitness indicators and demographic information.

**Variables include:**  
- Age  
- Weight and height  
- Aerobic capacity (VO2 max)  
- Lifestyle factors  

VO2 max can influence HRV, sleep quality, and energy levels.

---

## 5. exercise.csv
**Purpose:**  
Tracks weekly or daily exercise patterns, used to understand how physical activity affects symptoms.

**Variables include:**  
- Exercise frequency  
- Exercise duration  
- Exercise type  
- Intensity level  

Exercise can improve mood and sleep, but may worsen symptoms for some individuals.

---

## 6. hormones_and_selfreport.csv
**Purpose:**  
Links subjective symptoms with hormonal cycle phases.

**Variables include:**  
- Hormone phase or cycle day  
- Self-reported symptoms  
- Ovulation markers  
- Mood or energy ratings  

This helps align symptom patterns with menstrual phase, which is essential in endometriosis monitoring.

---

## Summary
Each dataset supports different aspects of the flare-prediction process. Together, they form a realistic multi-modal dataset, similar to what a digital health application would collect from wearables, symptom trackers, and lifestyle logs.
