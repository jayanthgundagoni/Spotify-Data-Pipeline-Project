# Spotify-Data-Pipeline-Project

## Introduction
In this project, I implemented a complete data pipeline using Spotify. I integrated with the Spotify API to extract data and deployed the extraction code on AWS Lambda. I added triggers to run the extraction automatically and wrote a transformation function. I also set up automated triggers for the transformation process and ensured proper storage of files on S3. Finally, I built analytics tables on the data files using AWS Glue and Athena to enable detailed analysis.

## Overview

The project leverages below AWS services:

**1. AWS Lambda:** Handles data extraction and transformation.

**2. Amazon CloudWatch:** Schedules and triggers Lambda functions.

**3.Amazon S3:** Stores both raw and transformed data.

**4.AWS Glue:** Infers schema and creates a data catalog.

**5.Amazon Athena:** Queries data stored in S3.

## Architecture

![Data Flow Diagram](https://github.com/jayanthgundagoni/Spotify-Data-Pipeline-Project/blob/main/Spotify_DFD.jpg)


**1. Data Extraction:** Every day, an AWS Lambda function is automatically triggered by Amazon CloudWatch. This function accesses the Spotify API to gather data. Once collected, this data is saved in its raw form into an Amazon S3 bucket.

**2. Data Transformation:** When new data is added to the raw data S3 bucket, it triggers another Lambda function. This function processes the raw data, transforming it into a different format suitable for analysis. The transformed data is then stored in a separate Amazon S3 bucket dedicated to holding processed information.

**3. Data Cataloging:** AWS Glue is employed to automatically analyze the format and structure of the transformed data stored in the S3 bucket. This process creates a detailed data catalog that documents the contents and schema of the data, making it easier to understand and use for further analysis.

**4. Querying:** To perform queries on the data stored in S3, Amazon Athena is utilized. This service allows users to run standard SQL queries directly on the data stored in Amazon S3, providing quick and efficient access to the information for analysis and reporting purposes.

**Conclusion:**

By leveraging AWS Lambda, S3, AWS Glue, and Athena, this data pipeline achieves seamless integration with Spotify’s API, ensuring reliable data extraction, transformation, and analysis capabilities. 
