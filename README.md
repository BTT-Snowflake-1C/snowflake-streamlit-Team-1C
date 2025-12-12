# 🏜️ Navigating Care Deserts: Arizona Social Vulnerability & Healthcare Access Dashboard

---

## 👥 Team Members

| Name | GitHub Handle | Contribution |
|----|----|----|
| Mahamadou Nimaga | @Mahamadou4 | Streamlit app development, Snowflake integration, dashboard architecture, AI assistant |
| Team Snowflake 1C | @sgubba1 | Data engineering, feature selection, exploratory analysis, modeling |
| Team Snowflake 1C | @zyanczy| Data engineering, feature selection, exploratory analysis, modeling |
| Team Snowflake 1C | @fizabajwa25 | Data engineering, feature selection, exploratory analysis, modeling |
| Team Snowflake 1C | @nitsujiang | Data engineering, feature selection, exploratory analysis, modeling |
| Team Snowflake 1C | @naima-01 | Data engineering, feature selection, exploratory analysis, modeling |

---

## 🎯 Project Highlights

- Built an interactive **Streamlit-on-Snowflake dashboard** analyzing healthcare access across Arizona counties  
- Combined **SVI, heat risk, and hospital capacity** into a single analytical view  
- Identified counties at highest risk of being **medical deserts**  
- Delivered **interpretable visual analysis** for policy and public health use  
- Integrated a **Snowflake Cortex AI assistant** for natural-language insights
- Built an interactive Streamlit dashboard deployed natively in Snowflake
- Combined SVI, heat risk, and hospital capacity into a single analytical view
- Identified counties at highest risk of being medical deserts
-	Delivered interpretable visual analysis for public health and policy use
-	Integrated a Snowflake Cortex AI assistant for natural-language insights

---

## 🧰 Tech Stack
	•	Snowflake (Snowpark, Cortex)
	•	Streamlit (Snowflake-native)
	•	Python (pandas, Altair)
	•	GitHub (version control and deployment)
---
⸻

## 👩🏽‍💻 Setup and Installation

This project runs **natively inside Snowflake Streamlit**.

**Environment**

Name: app_environment

Channels:
	•	snowflake

## Dependencies:
	•	python 3.10
	•	snowflake-snowpark-python
	•	streamlit

### How to Run
	1.	Connect this GitHub repository to Snowflake using Git integration
	2.	Open app.py in Snowflake Streamlit
	3.	Run the app (authentication handled automatically)

### 🧪 Data Sources
These datasets include county-level social vulnerability indicators, heat exposure metrics, population data, and licensed hospital capacity.
Snowflake tables used in this project:
	•	SVI.PUBLIC.ARIZONA_CLEAN
	•	SVI.PUBLIC.ARIZONA_2022_MAXTEMP
	•	SVI.PUBLIC.ARIZONA_LICENSED_HOSPITAL
	•	SVI.PUBLIC.SVI_HOSPITAL_MERGED
	•	SVI.PUBLIC.SVICLEANED

These datasets include county-level social vulnerability indicators, heat exposure metrics, population data, and licensed hospital capacity.

⸻

## 🏗️Project Overview

Connection to Break Through Tech AI

This project was developed as part of the Break Through Tech AI Studio, where fellows work on real-world, industry-aligned data science challenges using enterprise platforms and responsible AI practices.

**Host Context & Objectives**

The objective of this project is to identify and explain healthcare access gaps (“medical deserts”) in Arizona by analyzing how social vulnerability, heat exposure, population dynamics, and hospital capacity interact at the county level. social vulnerability, heat exposure, population dynamics, and hospital capacity intersect at the county level.

**Scope of Work**
	•	Data exploration and feature engineering using Snowflake
	•	County-level comparative analysis and interactive visualization
	•	Interpretability-focused model evaluation
	•	AI-assisted insight generation for non-technical stakeholders

**Real-World Significance**

Extreme heat and social vulnerability amplify healthcare inequities. This dashboard helps:
	•	Public health officials prioritize intervention areas
	•	Policymakers allocate healthcare resources more effectively
	•	Communities prepare for climate-driven health risks


### 📊 Application Pages
- Home — Overview and live data preview  
- Data Understanding — Raw vs engineered datasets  
- County Analysis — Population and vulnerability comparisons  
- Exploratory Visual Analysis — Hospitals, heat, and social barriers  
- Modeling & Evaluation — Performance interpretation  
- AI Assistant — Snowflake Cortex–powered Q&A


### 📊 Data Exploration
- Explored raw and engineered datasets directly from Snowflake
- Analyzed distributions, missing values, and county-level variation
- Identified patterns linking vulnerability, heat risk, and hospital access
- Used visual, interpretable EDA to support non-technical decision-makers


### 🧠 Model Development
	•	Evaluated multiple models (logistic regression, decision tree, random forest)
	•	Focused on interpretability over complexity
	•	Observed perfect scores due to small dataset size and clear signal
	•	Explicitly discussed risks of overfitting and data leakage
	

### 📈 Results & Key Findings
	•	All evaluated models achieved perfect precision and recall on the dataset
	•	Results indicate a strong, easily separable pattern rather than robust generalization
	•	High-risk counties consistently show overlap between social vulnerability, heat exposure, and limited healthcare capacity


### 🤖 AI Usage
	•	Integrated an AI Assistant powered by Snowflake Cortex
	•	Enables natural-language questions about counties, vulnerability, and healthcare access
	•	Designed for explainability and decision support, not automated decision-making
	•	No external API keys required

⸻

### ⚖️ Responsible AI Considerations
	•	County-level aggregation may hide within-county disparities
	•	Small sample size limits generalizability
	•	Perfect model performance flagged as a red flag, not a success metric
	•	Outputs are intended to support human judgment, not replace it

⸻

### 🚀 Next Steps
	•	Expand datasets beyond Arizona
	•	Add cross-validation and temporal analysis
	•	Integrate geospatial mapping layers
	•	Evaluate external validation data
	•	 Cross-validation with expanded datasets
- Cross-validation with expanded datasets  
- Geospatial mapping layers  
- Time-series heat analysis  
- External validation beyond Arizona
- ### Future Enhancements
- Cross-validation with expanded datasets  
- Geospatial mapping layers  
- Time-series heat analysis  
- External validation beyond Arizona  

⸻

### 🔐 Security & Authentication
	•	Uses Snowflake-native get_active_session()
	•	No hardcoded credentials
	•	AI powered by Snowflake Cortex, not external LLM APIs

	⸻


⸻

## 🙏 **Acknowledgements** (Optional but encouraged)

Thank your Challenge Advisor, host company representatives, TA.

⸻

© 2025 — Team Snowflake 1C❄️
Break Through Tech AI Studio
