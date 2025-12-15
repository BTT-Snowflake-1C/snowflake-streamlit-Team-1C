# 🏜️ Navigating Care Deserts: Arizona Social Vulnerability & Healthcare Access Dashboard
Snowflake 1C
--- 

## Team Members

| Name | GitHub Handle | Contribution |
|----|----|----|
| Mahamadou Nimaga | [Mahamadou4](https://github.com/Mahamadou4)| Streamlit development, Modeling|
| Team Snowflake 1C | [sgubba1](https://github.com/sgubba1) | Data engineering, exploratory analysis |
| Ziyan Chen | [zyanczy](https://github.com/zyanczy) | Data engineering, single variable exploratory analysis, Streamlit development |
| Team Snowflake 1C | @fizabajwa25 | Modeling evaluation |
| Team Snowflake 1C | @nitsujiang | Data Engineering, multi variable exploratory analysis  |
| Team Snowflake 1C | @naima-01 | Exploratory analysis |
| Team Snowflake 1C | @cindycastanon | Modeling |


## Project Highlights

- Built an interactive **Streamlit-on-Snowflake dashboard** analyzing healthcare access across Arizona counties  
- Combined **SVI, heat risk, and hospital capacity** into a single analytical view  
- Identified counties at highest risk of being **medical deserts**  
- Integrated a **Snowflake Cortex AI assistant** for natural-language insights
- Combined SVI, heat risk, and hospital capacity into a single analytical view

---



## Tech Stack
- Snowflake (Snowpark, Cortex)
- Streamlit (Snowflake-native)
- Python (pandas, Altair)
- GitHub (version control and deployment)
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
These datasets include county-level social vulnerability indicators, heat exposure metrics, population data, and licensed hospital capacity.
Snowflake tables used in this project:
- SVI.PUBLIC.ARIZONA_CLEAN
- SVI.PUBLIC.ARIZONA_2022_MAXTEMP
- SVI.PUBLIC.ARIZONA_LICENSED_HOSPITAL
- SVI.PUBLIC.SVI_HOSPITAL_MERGED
- SVI.PUBLIC.SVICLEANED

These datasets include county-level social vulnerability indicators, heat exposure metrics, population data, and licensed hospital capacity. They were sources from Arizona's Department of Health and NOAA.

---
## Project Overview

Connection to Break Through Tech AI

This project was developed as part of the Break Through Tech AI Studio, where fellows work on real-world data science challenges using enterprise platforms and responsible AI practices.

**Host Context & Objectives**

The objective of this project is to identify and explain healthcare access gaps (“medical deserts”) in Arizona by analyzing how social vulnerability, heat exposure, population dynamics, and hospital capacity interact at the county level. The project takes various factors into consideration since public health crises like medical deserts tend to have a myriad of factors that impact them.

**Scope of Work**
- Data exploration and feature engineering using Snowflake Notebooks and Databases
- County-level comparative analysis and visualizations (uni-factor and multi-factor)
- Model development (three types)
- Model evaluation using recall and precision
- AI-assisted insight generation for non-technical users

**Real-World Significance**

Extreme heat and social vulnerability amplify healthcare inequities. This dashboard can help:
- Public health officials prioritize intervention areas
- Communities better understand what factors impact their health risks
- Make large amounts of health and SVI data easier to access using our AI chatbot

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


### 📊 Data Exploration
- Explored raw and cleaned datasets directly from Snowflake
- Analyzed distributions, missing values, and county-level variation
- Identified patterns linking vulnerability, heat risk, and hospital access
	- Conducted single variable exploration as well as multi-variable exploration for all counties

- Visualizations: The goal is to explore the data and see if there are any counties with preliminary concerns for SVI or hospital access.
  
Visualization 1: Exploring Individual SVI Variables by County
<img width="1313" height="412" alt="image" src="https://github.com/user-attachments/assets/47093edf-a186-4ea7-871c-6fa17b45acff" />
Visualization 2: Comparing County SVI Scores to County Hospital Frequency
<img width="815" height="435" alt="image" src="https://github.com/user-attachments/assets/4827adf7-00a4-4711-a18c-8518de07366a" />


### Model Development
- Evaluated multiple models (logistic regression, decision tree, random forest)
- Focused on interpretability over complexity
- Observed perfect scores due to small dataset size and clear signal
- Explicitly discussed risks of overfitting and data leakage
	

### Results & Key Findings
- All evaluated models achieved perfect precision and recall on the dataset
- Results indicate a strong, easily separable pattern rather than robust generalization
- High-risk counties consistently show overlap between social vulnerability, heat exposure, and limited healthcare capacity


### AI Usage
- Integrated an AI Assistant powered by Snowflake Cortex
- Enables natural-language questions about counties, vulnerability, and healthcare access
- Designed for explainability and decision support, not automated decision-making
- No external API keys required
<img width="995" height="564" alt="Screenshot 2025-12-12 at 4 32 27 PM" src="https://github.com/user-attachments/assets/14a1c0d0-4f39-4137-9586-e57077eaed20" />



### Responsible AI Considerations
- County-level aggregation may hide within-county disparities
- Small sample size limits generalizability
- Perfect model performance flagged as a red flag, not a success metric
- Outputs are intended to support human judgment, not replace it

### Next Steps
- Expand datasets beyond Arizona
- Add cross-validation and temporal analysis
- Integrate geospatial mapping layers to highlight regional changes


## **Acknowledgements**

Thank you Rajshri Jain, Joe Warbington, Tess Dicker and Abhijay Rane!

© 2025 — Team Snowflake 1C ❄️
Break Through Tech AI Studio
