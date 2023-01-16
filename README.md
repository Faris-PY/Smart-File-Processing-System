# Smart-File-Processing-System
Azure Data Engineering

This Project gives insight into smart file processing using Azure.

![Architecture diagram](https://user-images.githubusercontent.com/107489749/212627066-d26b9305-3a12-463c-9e80-3f41afd2dc50.png)


## Resources used
1. Azure Databricks
2. Data Factory
3. Key vault
4. Datalake Gen2
5. SQL database


## Process step
1. The Internal Application place CSV files in Azure datalake storage.
2. The file will be received a day thrice.
3. Once the file is received, ADF will trigger the pipeline(using storage event trigger)
4. The ADF pipeline has databrick notebook associated with it.
5. Databrick will do the following operations
   * Check whether duplicate rows are present. If it contains duplicate rows, the file will be rejected and moved to a rejected folder in datalake for further analysis.
   * Validate the CSV file with the schema inferred from the database. If validation fails, the file will be moved to a rejected folder. If pass, the file will be transferred to the staging folder in datalake as well as to the delta table in DBFS


## Functionalities covered as part of This project
1. Batch processing, Role Based Access, Access Control List, Managed Identity
2. Data Factory - Storage Event trigger, Databrick notebook, Linked service, pipeline/activity parameter
3. Databricks - job cluster, all-purpose cluster, secret scopes, delta table.
4. Key vault - Keys, secrets
5. Datalake Gen2 - Shared Access Signatures (SAS), Lifecycle management
