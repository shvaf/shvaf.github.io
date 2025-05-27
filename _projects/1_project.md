---
layout: page
title: Determination of Deep Vein Thrombosis Diagnosis using Python and Natural Language Processing
description: Published May 26, 2025
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---

This project uses natural language processing and regular expressions in Python to identify diagnoses of Deep Vein Thrombosis (DVT) in dictated radiology reports. It was originally developed for a graduate student at Knight Cancer Research Institute who needed a fast, automated method to extract DVT diagnoses from 4,300 scanned reports.

## Skills Used
- Python  
- Natural Language Processing  
- Regular Expressions (Regex)  
- Sentiment Analysis  

## Background
To stay HIPAA compliant, the original dataset is not shared. Instead, I generated synthetic data using ChatGPT to demonstrate how the algorithm works. You can find this synthetic dataset in the repository: `ChatGPT_generated_fake_DVT_data.txt`.

## Initial Approach – Sentiment Analysis
I first explored sentiment analysis using the NLTK Python library, hoping that the tone of each report could serve as a proxy for diagnosis. While this approach was not effective for medical text, it demonstrated potential use cases for analyzing narrative clinical data. You can view this portion of the code in `DVT_Project_Python_Sentiment.py`.

> [Learn more about NLTK and sentiment analysis here](https://www.datacamp.com/tutorial/text-analytics-beginners-nltk)

## Final Approach – Regex
I ultimately relied on regular expressions to search for diagnostic keywords and determine whether they were negated or affirmed. If at least one positively identified diagnosis was found (with no negating terms), the scan was labeled positive for DVT. If only negated or non-relevant terms were found, it was labeled negative.

This method allowed for flexible, rule-based identification of diagnostic terms and their context, even when multiple body parts were described in a single report.

## Results
The final algorithm achieved **98% accuracy** when evaluated on a random sample of 200 reports manually reviewed against the automated output.

## Repository
Code, documentation, and example data can be found on GitHub:  
👉 [View the full project on GitHub](https://github.com/shvaf/DVT_Analysis/tree/main)
