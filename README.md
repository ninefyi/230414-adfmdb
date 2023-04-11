# Copy data from Azure Blob Storage to MongoDB Atlas Using Azure Data Factory
## Date: 14 Apr 2023
## Where: Microsoft Teams

## Preparing Environment

1. MongoDB Atlas
    - Cluster (Azure, eastasia region)
    - Private Endpoint
2. Azure
    - Virtual Machine
    - Virtual Network
    - Private Endpoint
    - Storage Account
    - Azure Data Factory

## STEPS

```shell
az datafactory pipeline create-run --factory-name "adfmdb" --parameters "{\"SourceStore_Location\":\"files\", \"SourceStore_Directory\":\"\", \"DestinationStore_Location\":\"files\", \"SourceStore_Directory\":\"done\"}" --name "CopyJsonToMongoDBAtlas" --resource-group "rg-demo"
```

