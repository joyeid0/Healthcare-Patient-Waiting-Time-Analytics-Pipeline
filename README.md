# Healthcare Patient Waiting Time Analytics Pipeline

## Project Overview

This project demonstrates a modern data engineering pipeline for analyzing patient waiting times in a healthcare environment.

The project uses data engineering concepts including data ingestion, Apache Spark processing, Delta Lake storage, data quality validation, and analytics generation.

The main goal is to transform raw hospital data into clean and trusted data that can support healthcare decision-making.

---

## Problem Description

Hospitals need to monitor patient waiting times to improve service efficiency and resource allocation.

The problem addressed in this project is:

*How can we analyze patient waiting times and identify departments with higher delays using a reliable data pipeline?*

---

## Data Source

The project uses a healthcare dataset containing patient visit information.

The dataset includes:

- Patient ID
- Department
- Arrival Time
- Service Time
- Waiting Time
- Patient Priority
- Visit Date

The data is stored in CSV format and used as the raw data source.

---

## Workflow / Architecture

The complete data pipeline follows these steps:

Raw Healthcare Data (CSV)  
↓  
Data Ingestion  
↓  
Apache Spark Processing  
↓  
Data Quality Checks  
↓  
Quality Gate  
↓  
PASS → Delta Lake → Analytics Output  
↓  
FAIL → Quarantine


---

## Data Processing Using Spark

Apache Spark is used to:

- Load raw healthcare data
- Remove duplicate records
- Handle missing values
- Transform data types
- Calculate waiting time metrics
- Prepare clean data for analysis

---

## Data Quality Checks

### 1. Completeness Check

Ensures important fields are not missing.

Examples:
- Patient ID cannot be empty
- Department cannot be empty
- Waiting Time cannot be null


### 2. Uniqueness Check

Ensures duplicate records are detected and removed.


### 3. Validity Check

Ensures data values follow business rules.

Examples:
- Waiting Time must be greater than or equal to zero.
- Department values must be valid.

---

## Quality Gate

A PASS/FAIL quality gate was implemented.

### PASS

If the dataset passes all quality checks:

Data → Delta Lake → Analytics


### FAIL

If the dataset fails quality checks:

Data → Quarantine


---

## Delta Lake

Delta Lake is used to store validated healthcare data.

It provides:

- Reliable storage
- Data versioning
- Improved data quality management

---

## Analytics Output

The final analytics output provides insights about hospital waiting times.

Example:

| Department | Average Waiting Time |
|------------|---------------------|
| Emergency | 40 minutes |
| Cardiology | 55 minutes |
| Dental | 20 minutes |

---

## Technologies Used

- Python
- Apache Spark
- Delta Lake
- Pandas
- Jupyter Notebook
- GitHub

---

## How to Run the Project

1. Install required libraries## How to Run the Project

1. Install required libraries:

pip install pyspark pandas delta-spark

2. Open the project notebook.

3. Run the notebook cells sequentially.

4. The pipeline will execute:
- Data ingestion
- Spark processing
- Data quality checks
- Delta Lake storage
- Analytics generation

---

## Future Improvements

Possible future improvements:

- Add real-time patient data streaming.
- Implement Machine Learning models to predict waiting times.
- Create interactive dashboards.
- Integrate hospital APIs.

---

## Results

The project successfully demonstrates:

✅ Data ingestion pipeline  
✅ Spark data processing  
✅ Data quality validation  
✅ PASS/FAIL quality gate  
✅ Delta Lake storage  
✅ Healthcare analytics output
