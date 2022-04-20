# AWS_ETL_Using_Glue_Redshift

**Main goal of this project** is to transfer Cardiology Categorical data(.CSV file) from S3 bucket through AWS Glue to Amazon Redshift for data storage and analysis purpose.

1) Initially I created a bucket and uploaded cardilogycategorical.csv object into my S3 bucket.
2) Now I created two Amazon SQS (one is normal queue and the other is Dead Letter Queue), here I created this messaging queue for whenever the object or file is uploaded or deleted from my bucket it should trigger and acts like a temporary repository for storing my messages. 
3) Now I created a Crawler in AWS Glue to extract cardilogycategorical.csv file data from S3, for that I created an IAM role with AmazonS3ReadOnlyAccess Bucket and DynamoDBFullAccess policies to it, and also created a temporary data for Glue to store metadata of that .csv file.
4) Now I created a 1 free-tier cluster using Amazon Redshift service, and created a table in redshift editor with cardilogycategorical name.
5) Now again coming back to AWS Glue, when crawler run is succeeded, go to database and check for the metadata of that table. 
6) Then after create new crawler to transfer data from AWS Glue to redshift. Now set IAM role and target to which we wants to send the data. Once if we created all settings, run this crawler to create a temporary data i.e, metadata into DB. Here you can also observe the mapping between the two crawlers metadata.
7) Now go to redshift editor and set the Database connection once again and start querying to get the data from AWS Glue to redshift. In this redshift we can use this for storage purpose or to analyze the data.
8) We can also perform the visual representation between two columns in a table.
9) We can go to the cloudwatch logs in AWS to check for glue log retention,monitoring and access control settings under log streams.  

**FEW OUTPUT FILES ARE ATTACHED ABOVE**
