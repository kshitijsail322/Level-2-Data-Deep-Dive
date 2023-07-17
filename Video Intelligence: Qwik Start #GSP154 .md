# GSP154
## Run in cloudshell
```cmd
gcloud services enable videointelligence.googleapis.com
gcloud iam service-accounts create quickstart
gcloud iam service-accounts keys create key.json --iam-account quickstart@$DEVSHELL_PROJECT_ID.iam.gserviceaccount.com
gcloud auth activate-service-account --key-file key.json
echo -e "\033[31mhttps://www.youtube.com/@CodingWithHardik\033[0m"
gcloud auth print-access-token
cat > request.json <<EOF
{
   "inputUri":"gs://spls/gsp154/video/train.mp4",
   "features": [
       "LABEL_DETECTION"
   ]
}
EOF
echo -e "\033[31mhttps://www.youtube.com/@CodingWithHardik\033[0m"
export RESPONSE=$(curl -s -H 'Content-Type: application/json' -H 'Authorization: Bearer '$(gcloud auth print-access-token)'' 'https://videointelligence.googleapis.com/v1/videos:annotate' -d @request.json | jq -r '.name')
echo -e "\033[31mhttps://www.youtube.com/@CodingWithHardik\033[0m"
curl -s -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer '$(gcloud auth print-access-token)'' \
    'https://videointelligence.googleapis.com/v1/$RESPONSE'
```
