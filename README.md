# Bellabeat Consumer Health Analytics Case Study

> **Role:** Data Analyst  
> **Tools Used:** Tableau, Microsoft Excel, Microsoft Word  
> **Project Overview:** A deep-dive analysis of smart device consumer habits to identify trends in physical activity, user behavior personas, and sleep quality to drive strategic marketing recommendations.


---

## 1. Introduction & Business Task
### Project Context:
The Bellabeat dataset is a highly valued public resource that has been utilized and thoroughly analyzed by many in the data community. Building upon that collective foundation, my goal for this case study was to look closely at the data through a product-strategy lens—specifically connecting daily movement habits with nighttime rest patterns to uncover practical, actionable ideas for the Bellabeat app and hardware.

The Scenario
Founded in 2013, Bellabeat is a high-tech manufacturer of beautifully designed health and wellness smart devices for women. By tracking biometric data like activity, sleep, and stress levels, Bellabeat empowers women with knowledge about their own health and habits.
As a Data Analyst, my goal is to analyze smart device fitness data from consumers to identify key usage trends. These insights will directly inform and optimize Bellabeat's global marketing and product strategy, unlocking new growth opportunities for the brand.


---
## Business Task & Objectives
To analyze open-source Fitbit consumer data to identify trends in smart device usage, and use those behavioural insights to answer three core questions:
1.	What are some trends in smart device usage?
2.	How could these trends apply to Bellabeat customers?
3.	How can Bellabeat use these trends to help guide its marketing strategy?

## 2. Data Preparation, Integrity, & Limitations
### The Dataset
The analysis utilizes the public domain FitBit Fitness Tracker Data (stored on Kaggle via Mobius). The dataset contains personal fitness tracker metrics from anonymous Fitbit users, tracking daily activity, steps, sleep, and weight properties over a 31-day period.
       
### Data Integrity & Auditing (The Detective Phase)
While standard documentation suggests a sample size of 30 users, I initiated my analysis by checking data integrity. By applying an Advanced Filter in Excel to isolate unique identifiers, I discovered that the dataset actually tracks 33 unique user IDs across the activity sheets.
### Crucial Data Limitations & Strategic Scope
During the preparation phase, I evaluated the viability of the weightLogInfo_merged dataset and uncovered a Sample Size Bias.

•**Data Sparsity**: Out of the 33 unique users in the study, only 8 unique users actively recorded their weight.

•**The Analyst Decision**: Because roughly 75% of the participants completely abandoned the weight tracking feature, using this data to form a definitive conclusion would create a massive statistical bias.

•**The Pivot**: I made the analytical choice to exclude weight metrics from the core baseline trends. Instead, I pivoted this lack of data into a strategic user-engagement finding regarding the friction of manual data entry for consumers.


