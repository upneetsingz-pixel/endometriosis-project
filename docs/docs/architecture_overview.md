# Architecture Overview

This document provides a high-level overview of the conceptual architecture for the EndoTrack digital health platform, including data flow, components, and how information moves between patients, the app, the backend, and clinicians.

---

## 1. High-Level Components

- Patient mobile application  
- Wearable devices (for example, smartwatch, fitness band)  
- Cloud backend and database  
- Analytics and rules engine  
- Clinician-facing summary interface or dashboard  

---

## 2. Data Flow

1. **Data Capture (Patient and Wearables)**  
   - The patient uses the EndoTrack app to log:
     - daily pain scores  
     - symptoms (GI, mood, bleeding)  
     - fatigue and other factors  
   - Wearable devices send:
     - HRV or related metrics (if available)  
     - sleep duration and quality  
     - wrist temperature or related signals  

2. **Data Ingestion and Storage**  
   - The mobile app sends symptom and wearable data securely to a cloud backend.  
   - Data is stored in a structured format (for example, relational database tables or time-series storage).  

3. **Processing and Feature Engineering**  
   - A processing layer computes:
     - rolling averages (sleep, temperature)  
     - deviation from baseline metrics  
     - symptom severity indices  
     - cycle-phase alignment  

4. **Rules and Analytics Engine**  
   - Rule-based flare logic (as described in `flare_risk_rules.md`) is applied:  
     - checks for sustained severe pain  
     - evaluates sleep disruption patterns  
     - checks for temperature deviations  
   - Composite flare risk scores are generated.  
   - Data can be clustered to identify symptom phenotypes.

5. **Output and Visualization**  
   - Patients see:
     - daily wellness and flare risk indicators  
     - symptom and trend charts  
   - Clinicians see:
     - aggregated monthly or visit-based summaries  
     - trends across time  
     - flags for potential high-risk periods  

---

## 3. Conceptual Technology Stack

Although this implementation is conceptual, a realistic stack might include:

- Mobile app: iOS/Android using a cross-platform framework  
- Backend: REST API or FHIR-compatible services  
- Database: Relational database for structured data; time-series database for wearable metrics  
- Analytics: Python-based data pipelines or scheduled jobs  
- Dashboard: Web application for clinician review  

---

## 4. Alignment with Clinical Workflows

- Designed to complement existing care rather than replace it  
- Generates structured outputs that could be incorporated into an EHR visit note  
- Focuses on interpretable, rule-based logic that clinicians can understand and critique  
- Supports shared decision-making by surfacing patterns that might otherwise be missed in routine visits  

---

## Summary

The EndoTrack architecture connects patient-reported data, wearable signals, and rule-based analytics into a coherent pipeline. It demonstrates how a modern digital health tool for endometriosis could be structured to support both self-management and clinician insight.
