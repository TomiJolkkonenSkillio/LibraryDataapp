# Azure Synapse Analytics ETL groupwork

Analysis on finnish public library loan data from 2014 to 2023, combined with population structure data on finnish municipalities.Column names and the report is in finnish as the audience was finnish speaking in this case.

Project included design and implementation of ETL process in Azure Synapse Analytics and analysis and visualization on the data. Deliverables included a Power BI report and the documentation of the work as a presentation. The objective was to find interesting findings and correlations between different population groups and loan categories.

Tech used:
- Azure
- Azure Blob Storage
- Azure Synapse Analytics
- Dataflows
- PySpark notebook
- Power BI
- DAX measures

# Medallion structure

We used medallion structure for all datasets with the following logic:

- bronze level: raw data from public API's to Azure storage account
- silver level: unifying datasets from different years, more readable, data cleaning and modifications, filtering unrelevant data
- gold level: "hybrid star schema", fact and dimension tables, relations defined

# ERD for data

![ERD_library](https://github.com/user-attachments/assets/ba0cd231-602e-455a-8462-9ad05d0de9e2)

The main idea here for having two different fact tables was to separate the loan and collection amounts that are tied to dim_categories in addition to dim_years and dim_municipalities from population/economy data which are only tied to dim_years and dim_municipalities. The dimension tables are chosen and created thinking of easy and relevant grouping in Power BI.

# Analysis

![image](https://github.com/user-attachments/assets/7671a76b-bbba-42b5-ae62-2e4e4e216c44)

Interactive Power BI app using scatter plots to show correlations.
