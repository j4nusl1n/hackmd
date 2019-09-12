# Building Serverless Datalake using AWS
###### tags: `aws` `athena` `datalake` `serverless`

### Handson labs
 - [lab 1](https://kimsharing.s3.amazonaws.com/2019-09-13-Handson-ServerlessDataLakeDayLab1.pdf?AWSAccessKeyId=AKIAJXFERAZG3IRDYXEA&Signature=C%2BK198PQvH2Uj9YO8Ww/d/qvYZw%3D&Expires=1568821127)

### AWS Glue
  - 可以建立爬蟲去自動爬S3檔案的內容並且建立好schema
  - schema更動會自動更新版本，可以透過切換版本去檢視更動


### AWS Athena
  - Presto
  - Supported data formats: CSV, JSON, ORC, Avro, Apache Parquet
  - [tuning Athena](https://aws.amazon.com/blogs/big-data/top-10-performance-tuning-tips-for-amazon-athena/)
  - can use ElasticSearch as intermediate layer between S3 & Athena for fastening query
  - Don't use Athena for realtime query
  - Common issues:
    - 503 Slow down: request per seconds exceeded. 
      - possible solution: combine small files
    - Only support querying S3 data
    - JSON format: single line
    - Slow query:
      - partition data
      - optimize file sizes



### AWS Quicksight
  - [pdf](https://2019-new-jc-vue.s3-ap-northeast-1.amazonaws.com/Serverless-DataLake-Workshop-Quicksight.pdf)
  - serverless business intelligence service
  - data sources: AWS, mysql, local files. no GCP sources
  - not as flexible as Redash


### AWS LakeFormation
  - integrate all steps in building data lake architect like Kinesis -> Glue -> S3 -> Athena
  - grant table/column-level permissions
  - priced by other AWS services using (Kinesis, Glue, S3, Athena, ...). 

