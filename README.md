# Spotify End-To-End AWS Project

### Introduction
In this project, I've developed a robust ETL (Extract, Transform, Load) pipeline leveraging the Spotify API on AWS. This pipeline efficiently retrieves data from the Spotify API, transforms it into the desired format, and seamlessly loads it into an AWS data store.

### Architecture
![Screenshot of Architecture of Project](https://github.com/ManasP160/spotify-end-to-end-aws-project/blob/main/Architecture%20of%20Project.png)

### About Dataset/API
This project utilizes a dataset sourced from the Spotify API, specifically from the Top Songs Global Playlist. The dataset contains detailed information about the top songs globally, including the artist's name, album, song title, and various other metadata. This data is dynamic and is regularly updated, reflecting the latest trends with updates occurring daily.

[Spotify API Documentation](https://developer.spotify.com/documentation/web-api)

### Services Used
1. **S3(Simple Storage Service)** : Amazon S3 (Simple Storage Service) is a highly scalable object storage solution that can store and retrieve unlimited data from anywhere on the web. It's widely used for storing and distributing large media files, data backups, and static website content.
2. **AWS Lambda** : AWS Lambda is a serverless computing service that lets you run your code without managing servers. You can use Lambda to run code in response to events like changes in S3, DynamoDB, or other AWS services.
3. **Amazon CloudWatch** : Amazon CloudWatch is a monitoring service for AWS resources and the applications you run on them. You can use CloudWatch to collect and track metrics, collect and monitor log files, and set alarms.
4. **Data Crawler** : AWS Glue Crawler is a fully managed service that automatically crawls your data sources, identifies data formats, and infers schemas to create an AWS Glue Data Catalog.
5. **AWS Glue Data Catalog** : AWS Glue Data Catalog is a fully managed metadata repository that makes it easy to discover and manage data in AWS. You can use the Glue Data Catalog with other AWS services, such as Athena.
6. **Amazon Athena** : Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. You can use Athena to analyze data in your Glue Data Catalog or in other S3 buckets.

### Packages installed
```
pip install pandas
pip install spotify
pip install numpy
```

### Project Execution Flow 

1. **Extract Data from API** : Data is extracted from the Spotify API.
2. **Lambda Trigger (Every 1 Hour)** : A Lambda function is triggered every hour to initiate the extraction process.
3. **Run Extract Code** : The extraction code runs to retrieve the latest data.
4. **Store Raw Data** : The raw data is stored in an Amazon S3 bucket.
5. **Trigger Transform Function** : Another Lambda function is triggered to process the raw data.
6. **Transform Data and Load It** : The data is transformed into the desired format and loaded into a specified AWS data store.
7. **Query Using Athena** : Amazon Athena is used to query and analyze the processed data.
