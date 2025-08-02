# # Excel Salary Dashboard
![Recording2025-08-02092421-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/bfa33ea0-1d9e-4c49-9247-4cde23205892)

## Overview

The Excel Salary Dashboard was designed to help job seekers explore compensation trends in data-related roles. By visualizing salary ranges, job titles, locations, and required skills, the dashboard enables users to make informed decisions about their career trajectory.

### 📊 Dashboard File
You can view the final dashboard here: [Salary_Dashboard_Project.xlsx](Salary_Dashboard_Project.xlsx)

## Excel Techniques Applied

The project leverages a range of Excel functionalities to analyze and present the data effectively:

- **📉 Charts** – for clear visual representation of key metrics  
- **🧮 Formulas and Functions** – to compute summaries and derive insights  
- **❎ Data Validation** – to enable interactivity and maintain consistency

## About the Dataset

The dataset consists of real-world data science job listings from 2023. It includes detailed information such as:

- **👨‍💼 Job titles**
- **💰 Salary ranges**
- **📍 Job locations**
- **🛠️ Required skills**

The dataset provides valuable insights for those navigating the evolving data job market.

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries – Bar Chart

<img width="825" height="473" alt="Screenshot 2025-08-02 101823" src="https://github.com/user-attachments/assets/54e1663c-361f-4a78-922e-5ea533492ec5" />

- 🛠️ **Excel Features:** Implemented bar chart with formatted salary values and a layout optimized for clarity.
- 🎨 **Design Choice:** Horizontal orientation chosen to facilitate easier comparison across roles.
- 📉 **Data Organization:** Job titles are sorted by descending salary for immediate visual impact.
- 💡 **Insights:** Highlights clear trends, with senior and engineering roles commanding higher salaries than analyst positions.

#### 🗺️ Country Median Salaries – Map Chart

![map](https://github.com/user-attachments/assets/ae8e002a-5e03-4de2-a6a8-695783cbe4eb)

- 🛠️ **Excel Features:** Leveraged Excel's map chart to present geographical salary distribution.
- 🎨 **Design Choice:** Color-coded visualization enhances region-by-region comparison.
- 📊 **Data Representation:** Displays median salary by country based on available data.
- 👁️ **Visual Enhancement:** Optimized for quick interpretation of regional disparities.
- 💡 **Insights:** Reveals global salary variations and helps pinpoint high-paying locations.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Title

```
=MEDIAN(
IF(
(jobs[job_title_short]=A2)*
(jobs[salary_year_avg]<>0)*
(jobs[job_country]=contry)*
(ISNUMBER(SEARCH(type,jobs[job_schedule_type]))),
(jobs[salary_year_avg])
)
)
```

- 🔍 **Multi-Criteria Filtering:** Filters based on job title, country, and schedule type while excluding missing salary values.

- 📊 **Array Formula:** Combines `MEDIAN()` with a nested `IF()` to return a dynamic, criteria-based median.

- 🎯 **Tailored Insights:** Outputs salary figures that are specific to the combination of job title, location, and schedule type.

- 🔢 **Purpose:** Feeds a summary table that updates based on selected filters, ensuring the dashboard reflects contextual salary data.

🍽️ Supporting Data Table

<img width="426" height="382" alt="job_title_short_sorted" src="https://github.com/user-attachments/assets/3bdfaf80-5c29-4783-ae2f-78094a341022" />

📉 Dashboard Integration

<img width="332" height="511" alt="job_title" src="https://github.com/user-attachments/assets/0ac6eed3-6b4b-497f-a61d-043510035908" />

#### ⏰ Count of Job Schedule Type

```
=FILTER(K2#,NOT(ISNUMBER(SEARCH("and",K2#)))*(K2#<>0))
```

- 🔍 **Unique List Filtering:** Uses the `FILTER()` function to remove job schedule types containing the word "and" (often indicating compound labels) and to exclude zero values.

-  **🔢 Purpose:** Generates a clean list of individual job schedule types, used for accurate filtering and categorization in the dashboard.

🍽️ Supporting Data Table  

<img width="332" height="186" alt="job_schedule_type_sorted" src="https://github.com/user-attachments/assets/1a8fc6f2-3053-4155-8e4b-a79cbd2de1f0" />

📉 Dashboard Integration  

<img width="338" height="405" alt="type_dashboard" src="https://github.com/user-attachments/assets/e5f3ef0b-09b0-472b-bb97-0fcc6339f7ad" />

### ❎ Data Validation

#### 🔍 Filtered Input Selection

- 🔒 **Enhanced Data Control:** Applied data validation rules to the `Job Title`, `Country`, and `Type` selectors within the dashboard.
    - 🎯 Restricts user input to verified options only
    - 🚫 Prevents inconsistent or invalid entries
    - 👥 Improves dashboard interactivity and reliability

![job_title_gif-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/4358ee38-542c-4390-901e-ac408f261eda)

## Conclusion

This Excel dashboard offers valuable insights into salary trends across various data-related job roles. By analyzing job titles, locations, schedule types, and median salaries, it empowers users to make more informed decisions about their careers. The interactive features, visualizations, and clean data structure create a tool that's both informative and user-friendly.

