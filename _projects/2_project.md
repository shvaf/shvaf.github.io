---
layout: page
title: Using SQL to Build a Cohort to evaluate Diabetes & ED Visits 
description: Updated May 29, 2025
img: assets/img/diabetes.jpg
importance: 1
category: work
giscus_comments: true
---

## Project: Cohort Builder – Diabetes + ED Visits

This SQL script defines a real-world-style cohort of patients with:
- A first diagnosis of diabetes (excluding prediabetes)
- Diagnosed before age 40
- Who had an emergency department (ED) visit within 6 months of diagnosis

### Technologies and Skills Used
- PostgreSQL
- Common Table Expressions (CTEs)
- Window functions
- Clinical reasoning applied to synthetic EHR data
- Relational Databases

### Data Source 

The synthetic data comes from  SyntheaTM, an open-source patient population simulation made available by The MITRE Corporation which can be found at this [link](https://synthea.mitre.org/downloads). I used the 1k patient sample.

## Final Cohort

| patient                                | diabetes_start_date | age_at_diagnosis | encounter_start        |
|----------------------------------------|----------------------|------------------|-------------------------|
| 14dc5e57-1b84-3305-c042-86c9fc7e4996   | 12/29/2012           | 29               | 2013-02-09T04:21:38Z    |


Although the synthetic data only returns one patient meeting these criteria, the logic is easily extendable to other conditions or encounter types. The sample size is only 1000 patients and tweaking the criteria for age and time between diabetes diagnosis and ED visit did not increase the number of available patients. 

### Code Files

My GitHub repository containing the code can be found [here](https://github.com/shvaf/Diabetes-Cohort-in-SQL). 

### References
Jason Walonoski, Mark Kramer, Joseph Nichols, Andre Quina, Chris Moesel, Dylan Hall, Carlton Duffett, Kudakwashe Dube, Thomas Gallagher, Scott McLachlan, Synthea: An approach, method, and software mechanism for generating synthetic patients and the synthetic electronic health care record, Journal of the American Medical Informatics Association, Volume 25, Issue 3, March 2018, Pages 230–238, https://doi.org/10.1093/jamia/ocx079
