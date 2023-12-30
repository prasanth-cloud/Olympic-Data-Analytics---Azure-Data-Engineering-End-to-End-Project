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
5. App Registrations
6. PowerBI or Looker
## Data Ingestion
We already understood that we are using the Kaggle data - 2021 Olympics as our data source, then we will copy the data from data source to the ADLS using Azure data factory by creating linked service between azure data factory and the data source.

Firstly, we have created the Storage Account and containers with folders for storing the raw data and transformed data.

<img width="958" alt="storageacccondir" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/1f86ad3d-1353-4924-88fa-45594f3978b6">

Next, we will create the Azure Data Factory and make a connection with the source by creating linked connections.

<img width="958" alt="ADFlaunched" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/146b02ce-88e4-45d8-9715-893dfbc48128">

<img width="958" alt="ADFdataingestion" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/52d6071f-bc41-44c0-9ab7-97d4dfd7734a">


## Data Transformation
After the data gets stored in the Data Storage, then we will make another connection to azure databricks using an App registration service.

<img width="956" alt="Appregistered" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/8fddf288-465b-47ca-8bf3-703724ce1279">

<img width="959" alt="Certificatesecrets" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/7180328f-06b0-4fd1-b505-632adaf89188">

Note: Do not share the Client ID and Tenant Id with anyone and also the secret value.

there we will perform some pyspark transformations to filter the data , and change the datatypes of the data according to the requirement.

The used pyspark code in the project is under the code section. During the process , you might some error due to the access, there we should provide an access to the Storage Blob Data Contributor.

<img width="931" alt="givingaccesstoapp" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/f73b0cfc-e744-4ef4-93aa-d84e9a01a5b6">

<img width="679" alt="transformationmount" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/510eeed1-781e-4f5d-aa16-1005737e033c">

<img width="821" alt="questionanalysis" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/eb79d3d9-c912-4547-975e-dbbd0d2dd6ff">

<img width="821" alt="questionanalysis3" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/093965fb-da99-4806-af03-9a6214481eab">


After applying the above tranformations, again we will store the data into ADLS (data storage). From there, the azure synapse analytics uses the data from ADLS.

<img width="774" alt="Transformed_datafolders" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/e728592b-c02d-480d-a37b-b6a0387e05b9">

<img width="769" alt="Transformed_data" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/13d5014c-a697-4c43-af47-ff95a4640ac4">

## Data Loading
The penultimate step here after doing transformation is to do some analytics by loading the data to azure synapse analytics and find various insights from the transformed data.

<img width="958" alt="Asaanalysis" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/6798df32-a890-400d-94c2-1f8f22a853a5">


We can create Dashboards from the analytics data by using Power BI tool, which helps us to find the solutions in an easy and quick way by looking at the dashboard or at the reports.

## Result
The result of the whole ETL(Extract, Transform, Load) Data pipeline can be seen in the below reports/ Dashboards.
<img width="926" alt="piecharttransformation" src="https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/966f3fb4-f172-4fe2-9684-fb15374b8b93">

Some of the insights that we found from the data are which countries have won the number of Gold, Silver, Bronze and presented them in a Bar,Pie chart using the Synapse analytics service.

![image](https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/e61533bb-d91c-4263-9981-90a789a7fb0f)


![SQL script 3 (1)](https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/4baff88c-339a-448c-83de-001b10e6629b)

![SQL script 3 (3)](https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/72ca2ea7-27b3-4061-b132-fd8588bc27a1)
![SQL script 3 (2)](https://github.com/prasanth-cloud/Olympic-Data-Analytics---Azure-Data-Engineering-End-to-End-Project/assets/79701423/bd26fb00-c54b-4c72-acc4-bc6023f2ab06)


