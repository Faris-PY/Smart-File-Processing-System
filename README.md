# Smart-File-Processing-System
Azure Data Engineering

This Project give insight about smart file processing using Azure.

![Architecture diagram](https://user-images.githubusercontent.com/107489749/206750345-f9837e95-1239-4527-8473-affb88df114a.png)

## Resource used 
1. Azure Databricks
2. Data Factory
3. Key vault
4. Datalake Gen2
4. SQL database


## Process step

1. The Internal Application place CSV file in Azure datalake storage.
2. The file will be receiving thrice a day.
3. One the file received, ADF will trigger the pipeline(using storage event trigger)
4. The ADF pipeline has databrick notebook associated with it.
5. Databrick will do the following operations 
   - Check wheather duplicate rows present. If it contains duplicate rows, file will be rejected and moved in rejected folder in datalake for further analysis.
   - Validate the CSV file with the schema infered from the database. If validation fails, file will be moved to rejected folder. If pass, file will be moved to staging folder in datalake as well as to delta table in DBFS

## Functionalities covered as part of This project

1. Batch processing, Role Based Access, Access Control List, Managed Identity
2. Data Factory - Storage Event trigger, Databrick notebook, Linked service, pipeline/activity parameter 
3. Databricks - job cluster, all-purpose cluster, secret scopes, delta table.
4. Key vault - Keys, secrets  
5. Datalake Gen2 - Shared Access Signatures (SAS), Lifecycle management
