---
layout: page
title: Determination of Deep Vein Thrombosis Diagnosis using Python and Natural Language Processing
description: Published May 26, 2025
img: assets/img/dvt.jpg 
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

## Background on Deep Vein Thrombosis
Deep Vein Thrombosis (DVT) is a condition in which a blood clot forms in a deep vein, most commonly in the lower extremities. If left untreated, DVT can lead to serious complications such as pulmonary embolism (PE), a potentially life-threatening blockage in the lungs. Risk factors include prolonged immobility, recent surgery, cancer, and inherited clotting disorders [1][2]. Early and accurate diagnosis is critical for preventing morbidity and mortality.

## Introduction to the Project
DVT is only diagnosed via imaging and radiology reports. A graduate student from the OHSU School of Medicine contacted the Biostatistics Shared Resource (BSR) Center, where I was working, for help with a project involving over 4,300 such reports stored in a single text file. His goal was to determine whether each report contained evidence of a Deep Vein Thrombosis (DVT) diagnosis. Since multiple body locations were evaluated in each report, he was only interested in identifying if **any** location indicated a positive diagnosis per patient.

## Note on Data Source
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


## References 
[1] Centers for Disease Control and Prevention. (2020). *What is Venous Thromboembolism (VTE)?* https://www.cdc.gov/ncbddd/dvt/facts.html  
[2] Mayo Clinic. (2023). *Deep vein thrombosis (DVT)*. https://www.mayoclinic.org/diseases-conditions/deep-vein-thrombosis/symptoms-causes/syc-20352557  

