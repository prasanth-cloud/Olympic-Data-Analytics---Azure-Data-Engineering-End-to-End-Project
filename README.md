# Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project
In this project, we will be using the various Azure data services which are used for Data Ingestion, Transformation and loading . The services are Azure Datafactory, Azure Databricks, Azure Data Lake Storage Gen2(ADLS), Azure synapse analytics and Power BI.
## Project Overview
Here, we are extracting the data from an external data source using a service in azure called as Azure Datafactory, which is used to create piplines and to provide connection using various external sources. After making the connection, we will store the data in ADLS . Then we will perform the transformation by cleaning the data, removing the duplicates, and changing the datatypes according to the source file.


The transformed data has been then stored in another container in ADLS and move the data to Azure synapse analytics for analysis. In synapse analytics , we do query processing to find out the required insights from the data.


Finally, we will prepare the dashboard using power BI, or Looker Studio or Tableau. 
# Prerequisites
Basics of Python and SQL

Azure Account

## Data Source
Dataset from Kaggle - 2021 Olympics in Tokyo[Download here][https://www.kaggle.com/datasets/arjunprasadsarkhel/2021-olympics-in-tokyo?select=Teams.xlsx]

## Services/Tools Used
1. Azure Data Factory
2. ADLS Gen2
3. Azure Databricks
4. Azure Synapse Analytics
5. Power BI or Looker
## Data Ingestion
We already understood that we are using the Kaggle data - 2021 Olympics as our data source, then we will copy the data from data source to the ADLS using Azure data factory by creating linked service between azure data factory and the data source.

## Data Transformation
After the data gets stored in the Data Storage, then we will make another connection to azure databricks using an App registration service, then we will perform som pyspark transformations to filter the data , and change the datatypes of the data according to the requirement.

The used pyspark code in the project is as follows:

After applying the above tranformations, again we will store the data into ADLS (data storage). From there, the azure synapse analytics uses the data from ADLS.
## Data Loading
The penultimate step here after doing transformation is to do some analyticsby loading the data to azure synapse analytics and find various insights from the transformed data.

We can create Dashboards from the analytics data by using Power BI tool, which helps us to find the solutions in an easy and quick way by looking at the dashboard or at the reports.

## Result
The result of the whole ETL(Extract, Transform, Load) Data pipeline can be seen in the below reports/ Dashboards.

Some of the insights that we found from the data are which countries have won the number of Gold, Silver, Bronze and presented them in a bar chart using the Synapse analytics service.

![image](https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/e61533bb-d91c-4263-9981-90a789a7fb0f)


![SQL script 3 (1)](https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/4baff88c-339a-448c-83de-001b10e6629b)

![SQL script 3 (3)](https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/72ca2ea7-27b3-4061-b132-fd8588bc27a1)
![SQL script 3 (2)](https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/bd26fb00-c54b-4c72-acc4-bc6023f2ab06)


