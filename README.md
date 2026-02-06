### Health Clinic Data Summary & Outlier Analysis 

### Project Overview 
This project is a Python-based data pipeline designed for LifeCare Clinics. It automates the process of ingesting raw patient vital signs, calculating key health statistics, and flagging "high-risk" patients using the Interquartile Range (IQR) method for outlier detection.


### Dataset 
Source: Synthetic Data Generation

Description: The dataset (patient_vitals.csv) contains 35 records of patient health metrics, including Heart Rate, Temperature, and SpO2 levels.

Outlier Logic: I utilized a script to inject realistic physiological outliers (e.g., temperatures > 38°C) to test the robustness of the detection engine.


### Features 
Custom Statistics Engine: Implemented Mean, Median, Mode, and IQR from scratch without using external libraries like Pandas.

Robust Error Handling: The ingestion module uses try-except blocks to handle missing files and corrupted data rows (e.g., non-numeric values in numeric fields).

Modular Design: Code is organized into functional modules for ingestion, analysis, and reporting to ensure maintainability.


### Mathematical Logic 
To identify high-risk patients, the pipeline calculates the Interquartile Range (IQR) for vital signs: 
Q1 & Q3

Bounds: Lower Bound = Q1 - (1.5 * IQR) 
Upper Bound = Q3 + (1.5 * IQR)