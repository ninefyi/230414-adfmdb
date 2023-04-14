# Copy data from Azure Blob Storage to MongoDB Atlas Using Azure Data Factory

## Date: 14 Apr 2023

## Where: Microsoft Teams

## Preparing Environment

1. Create Service Principal for Azure Data Factory.

```az ad sp create-for-rbac \
--name "app-for-adf" \
--role contributor \
--scopes /subscriptions/<SubscriptionId>/resourceGroups/rg-demo
```

2. Run the following command to create all resources. ```./prepare.azcli```

3. Create MongoDB Atlas and Private endpoint.

4. Setup IR Self-Hosted Integration Runtime on Azure VM.

5. Import the pipeline from the file `CopyJsonToMongoDBAtlas.json`.

6. Upload the file `dataset/players-1.json` and `dataset/players-2.json` to the Azure Blob Storage.

7. Create folder `done` in the Azure Blob Storage and upload the file `dataset/empty` to the folder `done`.

8. Test the pipeline.

```
az datafactory pipeline create-run --factory-name "adfmdb" --parameters "{\"SourceStore_Location\":\"files\", \"SourceStore_Directory\":\"\", \"DestinationStore_Location\":\"files\", \"DestinationStore_Directory\":\"done\"}" --name "CopyJsonToMongoDBAtlas" --resource-group "rg-demo"
```
