EndoTrack: A Wearable-Integrated Endometriosis Detection & Management Platform
EndoTrack is a conceptual digital health platform designed to support earlier detection and ongoing management of endometriosis. It integrates symptom tracking, wearable signals, lifestyle factors, and clinically aligned rule-based decision support to generate meaningful insights for both patients and clinicians.
This repository contains datasets, analysis notebooks, prototype sketches, a final academic paper, and the project presentation.

1. Background
- Endometriosis affects an estimated 190 million people globally, yet diagnosis is often delayed 7–10 years due to:
- Vague and overlapping symptoms
- Lack of structured symptom tracking
- Limited integration of wearable and biometric data
- Insufficient decision-support tools for clinicians
- Most existing apps track pain or menstrual cycles only, without incorporating physiological biomarkers such as HRV, wrist temperature, or sleep patterns. They also lack guideline-based clinical insights.
- EndoTrack addresses these gaps through multi-modal data integration and clinically informed analytics.

2. Overview of EndoTrack
Patient-Facing Features
- Daily symptom logging (pain, mood, GI symptoms, bleeding)
- Integration with wearable data (HRV, sleep metrics, wrist temperature)
- Daily wellness scoring
- Flare Risk Index
- Cycle-phase–aligned trend analysis
- Alerts for sleep disruption or stress-related indicators
Clinician-Facing Features
- Automatically generated symptom and wearable data summaries
- Longitudinal trend visualizations
- Guideline-aligned insights based on NICE NG73
- Visit-ready reports
- Unsupervised clustering of symptom patterns to identify phenotypes
Rule-Based and Analytical Logic
- HRV decreases combined with pain severity thresholds
- Multi-day rolling averages for stable biomarker interpretation
- Sleep duration and temperature deviations used as flare indicators
- K-means clustering for symptom grouping

3. Repository Structure
EndoTrack/
│
├── datasets/               # Real datasets used for analysis
├── analysis/               # Jupyter notebooks (flare logic, trends, clustering)
├── prototype/              # Architecture and UI concept sketches
├── paper/                  # Final academic research paper
├── presentation/           # Project slide deck
└── docs/                   # Supplementary technical documentation

4. Methods Summary
Data Sources
- This project uses several datasets to simulate a wearable-integrated digital health environment:
- Structured endometriosis symptom reported data
- Sleep health and lifestyle dataset
- Wrist temperature dataset
- Exercise and VO2 max dataset
- Hormone and self-report data
- These datasets collectively support feature engineering and exploratory analysis.
Feature Engineering Approach
- Normalization of HRV readings
- Rolling averages (three-day and seven-day)
- Identification of temperature deviations
- Symptom severity scoring
- Alignment of symptoms with menstrual cycle phases
- Integration of symptoms and wearables into combined flare signals
Analytical and Machine Learning Concepts
- Trend visualization for wearable and symptom data
- Symptom trajectory analysis
- Correlation assessments (e.g., HRV vs. pain, sleep vs. fatigue)
- Rule-based flare detection
- K-means clustering to identify symptom subgroups
- Mapping insights to NICE NG73 guidelines

5. Prototype and System Architecture
The prototype demonstrates:
- End-to-end data flow from patient to clinician
- Core app screens (symptom log, trends, alerts, dashboard)
- Monthly clinician summary report logic
- Clinical decision-support elements
- High-level digital health architecture and workflow

6. How to Use This Repository
- Clone or download the repository.
- Install required Python packages if running analysis notebooks:
pip install pandas numpy seaborn matplotlib scikit-learn
- Open Jupyter notebooks in the analysis/ folder for exploratory analysis.
- Review prototype diagrams in the prototype/ folder.
- Read the final academic paper in the paper/ folder.
- View the slide presentation in the presentation/ folder.

7. Contribution Summary
This project includes contributions in:
- Concept development
- Dataset selection and integration
- Feature engineering and rule-based logic creation
- Wearable and symptom trend analysis
- Architecture and prototype design
- Academic research and presentation development
- The project demonstrates competencies in digital health, analytics, clinical guideline alignment, and conceptual machine learning applications.

8. Future Work
Planned or possible future extensions include:
- Adding a functional Streamlit prototype or dashboard
- Expanding clinician interface features
- Integrating ECG or PPG waveform analysis
- Implementing deep-learning models for sequence data
- Designing a fully functional backend API
