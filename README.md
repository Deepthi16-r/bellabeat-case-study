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

## 3. Data Processing & Tool Selection

To transition from raw data to meaningful insights, the data had to be thoroughly processed, cleaned, and verified. This phase ensures that the data is accurate, formatted correctly, and completely free of errors before analysis.

### Selection of Tools

* **DB Browser for SQLite:** Chosen for the data processing phase. Because the FitBit dataset contains thousands of rows of tracking data across multiple spreadsheets, DB Browser provides a powerful local environment to aggregate, filter, and join these tables using SQL.
* **Tableau:** Chosen for the data visualization phase to create an interactive, easy-to-read dashboard once the data was cleaned.

### Data Cleaning & Processing Strategy
Before running the final analysis, a strict cleaning checklist was established to maintain high data quality:

* [x] **Format Verification:** Ensuring dates and times were formatted correctly so they could be properly linked across different tables.
* [x] **Checking for Duplicates:** Running queries to find and remove any identical rows that could accidentally double-count user activity.
* [x] **Handling Missing Data:** Identifying blank cells or incomplete rows to ensure they wouldn't skew the final averages.
* [x] **Filtering Sample Sizes:** Verifying unique user IDs across tables, which led to the discovery of the 33-user activity vs. 24-user sleep split.

## 4. Data Exploration & Analysis

By analyzing the aggregated metrics across both datasets, a clear narrative emerged regarding how the typical consumer interacts with their fitness tracker. The data reveals that the average user is not an extreme fitness enthusiast, but rather an everyday individual balancing sedentary routines with pockets of activity.

### 📊 SQL Query Execution & Verification
To verify the query's success and document the relational output, the screenshot below captures the database execution environment. The query successfully reconciled the datasets, returning 24 distinct user rows in 24 milliseconds.

![SQL Query Execution] <img width="1920" height="965" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/84399e7c-4619-4432-b7e1-162917e8e665" />


---

### 🛋️ The Sedentary Reality
* **The Stat:** Users spend an overwhelming average of **991 minutes per day** completely sedentary.
* **The Story:** That equates to roughly **16.5 hours** of non-active awake time. This is a massive baseline metric. It proves that the typical user spends the vast majority of their day sitting—likely at a desk job or during a commute—making sedentary behavior the dominant state of their lifestyle.

---

### 📊 Consumer Segmentation: The 3 User Personas
To look past basic overall averages, a deeper user segmentation analysis was executed by grouping the 33 unique tracker users into custom behavioral personas based on their average daily step counts:

<img width="1920" height="997" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/b903106a-b575-4d39-8428-c22bf9028460" />




| Persona | % of Users | User Count | Behavioral Description |
| :--- | :--- | :--- | :--- |
| **Highly Active** | 21.2% | 7 / 33 | Consistently surpass the 10,000-step daily threshold. |
| **Moderately Active** | 54.5% | 18 / 33 | Consistently log between 5,000 and 10,000 steps a day. This represents the absolute majority of Bellabeat's consumer base. |
| **Sedentary Lifestyle** | 24.2% | 8 / 33 | Struggle significantly with movement, averaging fewer than 5,000 daily steps. |

> 💡 **Business Takeaway:** An overwhelming **78.7%** of tracker users do not meet standard daily activity goals. This indicates that Bellabeat's primary target audience is not elite athletes or gym enthusiasts, but everyday women balancing busy schedules who require gentle accountability, behavioral nudges, and habit-building features rather than raw performance metrics.

---

### 👟 The Step Gap & Everyday Movement
* **The Stat:** The average user logs **7,637 steps per day**, covering an average total distance of **5.4 kilometers** (approx. 3.3 miles).
* **The Story:** The universally recognized benchmark for a highly active, healthy lifestyle is 10,000 steps. The data shows our consumer base falls short of this goal by roughly 24%.
* **The "Everyday Active" Contrast:** Interestingly, users cover more than double the distance through casual, light daily movement (3.3 km) than they do through dedicated, high-intensity workouts or runs (1.5 km). This indicates that the user's activity is driven by daily chores, errands, and casual walking rather than intense gym sessions.

---

### 🛌 The Bedtime Friction & Sleep Struggle
<img width="1920" height="960" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/8f780d71-b479-4fbc-9d07-935e77cdfd86" />

* **The Stat:** Users spend an average of **459 minutes in bed**, but only **419 minutes actually asleep**.
* **The Story:** This reveals a consistent **39-minute gap** every single night. Users are sitting in bed awake—tossing and turning, reading, or scrolling on their phones—for nearly 40 minutes before falling asleep.
* **The 27% Drop-Off:** As proven by the SQL JOIN query, **27% of users stop tracking their data entirely at night**. This points to a comfort barrier: more than a quarter of users choose to remove the device before going to sleep.

