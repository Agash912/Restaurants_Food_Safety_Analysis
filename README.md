# Restaurants Food Safety Analysis

## Project Overview
Developed a food safety inspection analytics platform for eateries in Chicago and Dallas using government-provided datasets. The project involved data profiling and transformation, followed by dimensional modeling to organize data into facts and dimensions for analysis. Intuitive dashboards were designed to provide actionable insights into inspection outcomes, risk categories, violation patterns, and compliance trends. The platform aims to empower public health officials and decision-makers with data-driven tools to effectively monitor and enhance food safety standards.

- Tools Used: Alteryx, Microsoft Excel, Talend, ER Studio, Snowflake, SQL, Snowflake, PowerBI, Tableau
- [PowerBI Visualization Link]()
- [Tableau Visualization Link](https://public.tableau.com/app/profile/agash.uthayasuriyan/viz/Food_Inspection_Report_Agash/OverviewDashboard)

## Datasets Overview

### Chicago Dataset
Inspections are conducted by the Chicago Department of Public Health’s Food Protection Program using standardized procedures. Inspection results are entered into a database and reviewed by a State of Illinois Licensed Environmental Health Practitioner (LEHP).
[Link to Dataset](https://data.cityofchicago.org/Health-Human-Services/Food-Inspections/4ijn-s7e5/data_preview)

### Dallas Dataset
Inspections are conducted and the provided by Code Compliance Services Department, Consumer Health Division of Dallas.
[Link to Dataset](https://www.dallasopendata.com/Services/Restaurant-and-Food-Establishment-Inspections-Octo/dri5-wcct/about_data)

## Business Requirements
- Evaluate and categorize the outcomes of food inspections.
- Analyze different types of inspections conducted.
- Assess the risk level associated with each inspection.
- Examine inspection results across various types of facilities.
- Identify and analyze violations, including their codes and descriptions.
- Gain insights into businesses being inspected, including name, and licensing details.
- Analyze inspection data based on geographical locations.

## Project Steps

### Step 1: Understanding the Dataset, Business Requirements
- Analyzed the schema and content of the provided datasets.
- Devise a plan of execution to prepare the data to answer business requirements.

### Step 2: Data Profiling in Alteryx
- Imported datasets into Alteryx.
- Utilized Alteryx tools for data profiling and derived insights such as datatype, percentage of missing values, percentage of nulls, shortest and longest value along with inferences observed for each column.

### Step 3: Devising a Common Schema for the Final Table
- Designed a schema for the final table based on the data available in both datasets and the business requirements.

### Step 4: Data Transformation
- Addressed missing values by replacing nulls with -9999 for numerical columns and NA for text fields.
- Extracted meaningful attributes by splitting single columns into multiple and merging related columns.
- Removed junk text and irrelevant characters using regex patterns to enhance data quality.
- Capitalized all text for consistency, applied uniform decimal precision, and standardized timestamps to the desired format.
- Adjusted column values with zero-padding or truncation to ensure uniformity across datasets.
- Derived additional attributes to meet business requirements through calculated fields.
- Added audit columns for traceability.
- Loaded the transformed data into a final staging table in Snowflake, ensuring readiness for dimensional modeling.

  #### Pipeline created for Dallas:
  ![image](https://github.com/user-attachments/assets/e31cd183-f007-47d4-90c5-ddea4d03a80f)

  #### Pipeline created for Chicago:
  ![image](https://github.com/user-attachments/assets/493f5b90-28a1-444c-be06-849ae0ecb69c)

  #### Pipeline created to combine both datasets into one:
  ![image](https://github.com/user-attachments/assets/af5934b9-5106-4387-9777-9d934626d2f9)


### Step 5: Dimensional Modeling in ER Studio
- Designed a dimensional model based on business requirements, including fact and dimension tables.
- Generated a physical model and DDL scripts.
- Executed the scripts in Snowflake to create the dimensional schema.

  #### Dimensional Model Prepared:
  ![image](https://github.com/user-attachments/assets/9b42ee5a-52ac-4acd-afe6-b342d0fe1dd8)


### Step 6: Data Loading into Dimensional Models using Talend
- Loaded data into the dimensional model in Snowflake using Talend.
- Added audit columns to ensure data traceability.

  ![image](https://github.com/user-attachments/assets/a1bfcee6-4f23-4524-923b-d29ca1acb122)
  ![image](https://github.com/user-attachments/assets/47d904f0-16ad-476d-9dd4-3f0247d3eed5)
  ![image](https://github.com/user-attachments/assets/629b79e3-b310-4a4d-b063-72f7fda2359f)
  ![image](https://github.com/user-attachments/assets/fe0f18a2-3c8a-4098-a6b0-3f0e583a4ea8)
  ![image](https://github.com/user-attachments/assets/89145b78-32fa-40ae-85de-9fbcecadc322)
  ![image](https://github.com/user-attachments/assets/bf280064-0d46-4235-8680-a26c261bd58a)
  

### Step 7: Connecting to BI Tools
- Established connections to Snowflake in Tableau and Power BI.
- Focused on creating dashboards that are simple, clean, and highly functional for end-users.
- Positioned filters at the top beside the title for easy access, highlighted key performance indicators (KPIs) on the right, and arranged the remaining visualizations in the center.
- Ensured Tableau and Power BI dashboards mirrored each other in design, enabling business partners to switch between platforms seamlessly based on their convenience.
- Published dashboards to the cloud for accessibility and real-time monitoring.

  #### Power BI:
  ![image](https://github.com/user-attachments/assets/febbe74c-de81-4f50-9b2c-d51c419a1d10)

  ![image](https://github.com/user-attachments/assets/a06452d2-9acf-46b8-bb89-f2b4bcdec29d)

  #### Tableau:
  ![image](https://github.com/user-attachments/assets/b5c044cb-c9bc-4618-b6c2-7ea4dcb9505c)

  ![image](https://github.com/user-attachments/assets/3652a2cb-e969-42b9-8de4-8b02ff986771)

The prepared dashboard provide actionable insights to enhance food safety standards, improve compliance, and protect public health in Chicago and Dallas.
