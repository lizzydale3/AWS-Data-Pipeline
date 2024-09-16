# Comprehensive Analysis of the Iris Dataset Using AWS Data Pipeline and Visualization Tools

## Project Overview
This project demonstrates the use of AWS services to build a robust data pipeline that processes, analyzes, and visualizes the **Iris dataset**. The Iris dataset, a classic dataset in machine learning, is used to explore feature correlations and facilitate species classification. AWS services such as **Amazon S3**, **AWS Glue**, **Amazon Athena**, and **AWS QuickSight** were employed to create this data pipeline.

## Architecture Overview
The project is broken down into the following steps:
1. **Data Ingestion**: Upload the Iris dataset to **Amazon S3**.
2. **Data Processing**: Use **AWS Glue Crawler** to detect and register the schema of the dataset in the **AWS Glue Data Catalog**.
3. **Data Analysis**: Execute SQL queries on the data using **Amazon Athena** to perform analysis, including descriptive statistics and correlation analysis.
4. **Data Visualization**: Create visualizations using **AWS QuickSight** to provide insights into the relationships between the dataset features.

![Architecture Diagram](path_to_architecture_diagram.png)

## Technologies Used
- **Amazon S3**: For storing the dataset.
- **AWS Glue**: For schema detection and data processing.
- **Amazon Athena**: For querying the dataset using SQL.
- **AWS QuickSight**: For creating dynamic data visualizations.
- **SQL**: For data analysis and querying.

## Data Pipeline Stages

### 1. Data Ingestion and Storage
- The Iris dataset was sourced from the UCI Machine Learning Repository and uploaded to an **Amazon S3** bucket.
- **Amazon S3** was used due to its scalability and durability, ensuring reliable data storage and easy access for processing.

### 2. Data Processing and Transformation
- **AWS Glue Crawler** was used to automatically infer the schema of the dataset, registering it in the **AWS Glue Data Catalog**.
- The schema was customized by renaming columns for clarity, simplifying the querying process.

### 3. Data Analysis Using Amazon Athena
- SQL queries were executed in **Amazon Athena** to analyze the dataset directly from **Amazon S3**.
- **Descriptive statistics** such as mean, median, and standard deviation were calculated for each feature of the Iris dataset.
- **Correlation analysis** was performed to understand the relationships between features, which revealed strong correlations between petal dimensions.

Example SQL query for calculating descriptive statistics:
```sql
SELECT species, 
       AVG(sepal_length) AS avg_sepal_length, 
       AVG(sepal_width) AS avg_sepal_width, 
       AVG(petal_length) AS avg_petal_length, 
       AVG(petal_width) AS avg_petal_width
FROM iris_data
GROUP BY species;

