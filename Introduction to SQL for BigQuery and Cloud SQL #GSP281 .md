# GSP281
## Run in cloudshell
### Get Region from TASK 5
```cmd
export REGION=
```
```cmd
gsutil mb gs://$DEVSHELL_PROJECT_ID
curl -O -L https://github.com/CodingWithHardik/Level-2-Data-Deep-Dive/blob/master/files/start_station_data.csv
echo -e "\033[31mhttps://www.youtube.com/@CodingWithHardik\033[0m"
curl -O -L https://github.com/CodingWithHardik/Level-2-Data-Deep-Dive/blob/master/files/end_station_data.csv
gsutil cp start_station_data.csv gs://$DEVSHELL_PROJECT_ID
echo -e "\033[31mhttps://www.youtube.com/@CodingWithHardik\033[0m"
gsutil cp end_station_data.csv gs://$DEVSHELL_PROJECT_ID
gcloud sql instances create my-demo --database-version=MYSQL_5_7 --region=$REGION --tier=db-n1-standard-1 --root-password=""
echo -e "\033[31mhttps://www.youtube.com/@CodingWithHardik\033[0m"
gcloud sql connect my-demo --user=root --quiet
```
### Above cmd will ask for password just press enter dont put anything
```cmd
CREATE DATABASE bike;
```
