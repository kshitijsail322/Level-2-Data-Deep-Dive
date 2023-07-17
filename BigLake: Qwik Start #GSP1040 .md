# GSP1040
## Run in cloudshell
```cmd
bq mk --connection --location=US --project_id=$DEVSHELL_PROJECT_ID \
    --connection_type=CLOUD_RESOURCE my-connection
SERVICE_ACCOUNT_ID=$(bq show --format=json --connection $DEVSHELL_PROJECT_ID.US.my-connection | jq -r '.cloudResource.serviceAccountId')
gcloud projects add-iam-policy-binding $DEVSHELL_PROJECT_ID --member="serviceAccount:$SERVICE_ACCOUNT_ID" --role="roles/storage.objectViewer"
```
