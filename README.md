# Navigating Care Deserts: Arizona Social Vulnerability & Healthcare Access Dashboard

**Host:** Break Through Tech AI Studio × Snowflake  
**Team:** Snowflake 1C  

---

## Team Members

| Name | GitHub Handle | Main Contribution |
|----|----|----|
| Mahamadou Nimaga | [Mahamadou4](https://github.com/Mahamadou4)| Streamlit development, Modeling evaluation|
| Srinidhi | [sgubba1](https://github.com/sgubba1) | Data engineering, Exploratory analysis |
| Ziyan Chen | [zyanczy](https://github.com/zyanczy) | Data engineering, Single variable EDA, Streamlit development |
| Fiza Bajwa | [fizabajwa25](https://github.com/fizabajwa25) | Modeling evaluation, AI assitant |
| Justin | @nitsujiang | Data Engineering, Multivariable EDA  |
| Naima | @naima-01 | Exploratory analysis |
| Cindy | @cindycastanon | Modeling |


## Project Highlights ✨

- Built an **interactive Streamlit-on-Snowflake dashboard** analyzing healthcare access across Arizona counties  
- Integrated **Social Vulnerability Index (SVI), extreme heat risk, population dynamics, and hospital capacity** into a unified analytical view  
- Identified counties at highest risk of becoming **medical deserts**, especially during extreme heat events  
- Developed and evaluated **interpretable machine learning models** (logistic regression, decision tree, random forest)  
- Integrated a **Snowflake Cortex–powered AI assistant** for natural-language, explainable insights  

---
## Project Overview

### Objective

This project investigates how **extreme heat**, **social vulnerability**, and **healthcare capacity** interact to create *medical deserts* in Arizona. The goal is to identify counties where environmental risk and limited healthcare access overlap, particularly during heat emergencies.

### Motivation & Context

- Extreme heat is the **deadliest weather-related hazard** in the United States  
- Arizona experiences prolonged heat exposure from May through September  
- More than **4,300 heat-related deaths** occurred in Arizona between 2013–2024  
- Healthcare access varies widely across counties, and vulnerable populations face compounding barriers during emergencies  

### Business & Real-World Relevance

This dashboard is designed to support:

- **Public health officials** prioritizing intervention areas  
- **Policy makers** identifying structurally vulnerable regions  
- **Community organizations** understanding local drivers of health risk  
- **Non-technical users** accessing complex data through an AI-assisted interface  


### Scope of Work
- Data exploration and feature engineering using Snowflake Notebooks and Databases
- County-level comparative analysis and visualizations (uni-factor and multi-factor)
- Model development (three types)
- Model evaluation using recall and precision
- AI-assisted insight generation for non-technical users


### Repository Structure
- streamlit_app.py: Main Streamlit application file containing UI and page routing
- streamlitcopyfiza.py: Older version of Streamlit application file
- weather upload.ipynb: created the final dataset (SVI_HOSPITAL_MERGED) using various data sources and cleaning steps
- ziyan_eda_arizona.py: loads county-level health, social vulnerability, and heat data from Snowflake into the Streamlit


### Application Pages
- Home — Overview and live data preview  
- Data Understanding — Raw vs engineered datasets  
- County Analysis — Population and vulnerability comparisons  
- Exploratory Visual Analysis — Hospitals, heat, and social barriers  
- Modeling & Evaluation — Performance interpretation  
- AI Assistant — Snowflake Cortex–powered Q&A
<img width="402" height="470" alt="Screenshot 2025-12-12 at 4 52 28 PM" src="https://github.com/user-attachments/assets/44243dc6-6120-41ba-a4bd-5bf365416e20" />

---

## Data Exploration

### Data Sources

County-level datasets were accessed through **Snowflake**, sourced from the **Arizona Department of Health Services** and **NOAA**:

- Social Vulnerability Index (SVI) indicators  
- Heat exposure metrics (maximum temperature, 2022)  
- Licensed hospital locations and bed capacity  
- Population and daytime population estimates  

### Preprocessing & Assumptions

- Removed over **200 low-signal or redundant features**  
- Aggregated census-tract SVI data to the county level using **population-weighted averages**  
- Standardized county names to enable reliable dataset joins  
- Engineered **per-capita healthcare metrics** (e.g., hospitals and beds per 10k residents)  
- Flagged counties as *medical deserts* based on healthcare access thresholds  

### Exploratory Data Analysis (EDA) Insights

Key insights surfaced through single-variable and multi-variable visual analysis:

- **Greenlee, Santa Cruz, and Graham** fall in the bottom quartile for hospital access  
- **Apache and Yavapai** exhibit high heat vulnerability despite moderate temperatures  
- **La Paz, Gila, and Navajo** face overlapping poverty, uninsured rates, and transportation barriers  
- Heat risk and hospital capacity consistently emerge as the **strongest indicators** of medical desert status  


### Data Visualizations: 

Visualization from the EDA:
  
Visualization 1 (Single variable): Exploring Individual SVI Variables by County
<img width="1313" height="412" alt="image" src="https://github.com/user-attachments/assets/47093edf-a186-4ea7-871c-6fa17b45acff" />

Visualization 2(Multivariable): Comparing County SVI Scores to County Hospital Frequency
<img width="815" height="435" alt="image" src="https://github.com/user-attachments/assets/4827adf7-00a4-4711-a18c-8518de07366a" />

---

## Model Development

### Methods & Justification

Given the small dataset size and public-policy use case, we prioritized **interpretability over model complexity**:

- **Logistic Regression** — identifies statistical associations between features and medical desert status
<img width="827" height="667" alt="Screenshot 2025-12-14 at 11 35 38 PM" src="https://github.com/user-attachments/assets/e7ff1ece-b7dd-490d-bfc6-1ce2280618e8" />

- **Decision Tree** — provides transparent, rule-based explanations
<img width="828" height="523" alt="Screenshot 2025-12-14 at 11 36 00 PM" src="https://github.com/user-attachments/assets/ed72c45b-cc44-47da-89b8-6cdb658cf362" />

- **Random Forest** — highlights feature importance and robustness across models
<img width="1061" height="680" alt="Screenshot 2025-12-14 at 11 37 59 PM" src="https://github.com/user-attachments/assets/7562cc36-329b-41ae-910a-35f38129b603" />

Using multiple interpretable models allows us to verify whether the same structural patterns appear consistently rather than relying on a single algorithm.


### Training & Evaluation

- **Task:** Binary classification (medical desert vs. non-medical desert)  
- **Evaluation metrics:** Precision and recall  
- **Validation approach:** Evaluation on the full county-level dataset due to limited sample size  

#### Model Results

All three models (Logistic Regression, Decision Tree, Random Forest) achieved:

- **Precision:** 1.00  
- **Recall:** 1.00  
- **False Positives:** 0  

These results indicate that the dataset contains a **strong, easily separable signal** between medical desert and non-medical desert counties.


### Model Interpretation

- Logistic Regression coefficients suggest that **higher hospital capacity per capita strongly reduces medical desert risk**, though several coefficients are unstable due to multicollinearity  
- Decision Tree splits identify **heat risk** as the most informative variable for separating medical deserts from non-deserts  
- Random Forest feature importance consistently ranks **heat risk** and **hospital access per capita** as the top predictors  


### ⚠️ Important Note on Perfect Performance

Perfect model performance is treated as a **red flag rather than a success metric**:

- Perfect scores are rare in real-world data  
- The small dataset size increases the risk of **overfitting**  
- High multicollinearity among SVI variables limits coefficient interpretability  
- Results may not generalize to new regions or time periods  

As a result, these models are best understood as **exploratory and explanatory tools**, not production-ready predictive systems.

---

## Tech Stack
- Snowflake (Snowpark, Cortex)
- Streamlit (Snowflake-native)
- Python (pandas, Altair)
- GitHub (version control and deployment)

---

## AI Usage
- Integrated an AI Assistant powered by Snowflake Cortex
- Enables natural-language questions about counties, vulnerability, and healthcare access
- Designed for explainability and decision support, not automated decision-making
- No external API keys required
<img width="995" height="564" alt="Screenshot 2025-12-12 at 4 32 27 PM" src="https://github.com/user-attachments/assets/14a1c0d0-4f39-4137-9586-e57077eaed20" />


## Responsible AI Considerations
- County-level aggregation may hide within-county disparities
- Small sample size limits generalizability
- Perfect model performance flagged as a red flag, not a success metric
- Outputs are intended to support human judgment, not replace it

## Next Steps
- Expand datasets beyond Arizona  
- Add cross-validation and temporal analysis  
- Integrate geospatial mapping layers  
- Incorporate finer-grained (sub-county) data  

---

## Setup and Installation

This project runs **inside Snowflake Streamlit**.

**Environment**

Name: app_environment

Channels:
	•	snowflake

## Dependencies:
- python 3.10
- snowflake-snowpark-python
- streamlit

### How to Run
- Connect this GitHub repository to Snowflake using Git integration
- Open app.py in Snowflake Streamlit
- Run the app (authentication handled automatically)

### Data Sources

Snowflake tables used in this project:
- SVI.PUBLIC.ARIZONA_CLEAN
- SVI.PUBLIC.ARIZONA_2022_MAXTEMP
- SVI.PUBLIC.ARIZONA_LICENSED_HOSPITAL
- SVI.PUBLIC.SVI_HOSPITAL_MERGED
- SVI.PUBLIC.SVICLEANED

These datasets include county-level social vulnerability indicators, heat exposure metrics, population data, and licensed hospital capacity. They were sources from Arizona's Department of Health and NOAA.


## **Acknowledgements**

Thank you to **Rajshri Jain, Joe Warbington, Tess Dicker, and Abhijay Rane** for mentorship and guidance.

© 2025 — Team Snowflake 1C ❄️
Break Through Tech AI Studio
