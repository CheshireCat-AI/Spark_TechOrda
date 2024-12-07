# Restaurant and Weather Data Processing

## Overview
This project involves processing restaurant and weather datasets to create an enriched dataset that combines both, 
based on geographical location. The final data is saved in Parquet format, partitioned by country for easy access and processing.

---

## Steps Performed

### 1. Restaurant Data
- Merged restaurant data from several CSV files into a single DataFrame.
- Checked for incorrect or missing values in `latitude` and `longitude`. No gaps or incorrect values were found.
- Created a new column `custom_geohash` with `precision=4` based on `latitude` and `longitude` for each restaurant.
![image](https://github.com/user-attachments/assets/75ae9efb-0114-4fa6-9455-d3b7d0de59c7)

### 2. GeoHash Creation and Application
- Generated GeoHash values for both restaurant and weather datasets using `latitude` and `longitude`.
- For weather data, rows with missing coordinates were skipped to ensure consistency.
![image](https://github.com/user-attachments/assets/7694babf-4c93-4e44-8baf-e028d14bb8f3)

### 3. Merging Restaurant and Weather Data
- Merged restaurant and weather data using the `left-join` method on the `GeoHash` column.
- Found rows where weather data was missing (`NaN`), due to:
  - Limited regional coverage in the weather data.
  - Differences in data detail between restaurant and weather datasets.
- **Note:** The task requirements did not specify a strict check for the correctness of the GeoHash-based merge.
![image](https://github.com/user-attachments/assets/58a3f7cb-4c09-446f-9138-bb8302c197c0)

### 4. Saving Enriched Data
- The final enriched dataset was saved in Parquet format.
- Data was partitioned by the `country` column for ease of access and processing.
![image](https://github.com/user-attachments/assets/3adb0efa-da6f-4971-827b-982b0e2e6b31)
![image](https://github.com/user-attachments/assets/c7097dbd-bc89-44d4-93fc-7711fc17cba2)


