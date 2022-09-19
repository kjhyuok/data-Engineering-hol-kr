# AWS의 몇가지 서비스를 활용한 워크샵: data-Engineering-hol-kr

기존 [data-Engineering-hol](https://catalog.us-east-1.prod.workshops.aws/workshops/976050cc-0606-4b23-b49f-ca7b8ac4b153/en-US/)을 한글화 하고, 실습자에게 필요한 부분만 정리하여 구성합니다.

# Amazon Serverless를 이용한 실시간 버스 정보 수집 및 저장

본 github repository는 버스 정보를 주기적으로 수집하여 분석할 수 있도록, Amazon Serverless인 [Amazon Kinesis Data Stream](https://github.com/kyopark2014/technical-summary/blob/main/kinesis-data-stream.md), [Kinesis Data Firehose](https://github.com/kyopark2014/technical-summary/blob/main/kinesis-data-firehose.md), Lambda, DynamoDB, S3를 이용합니다. 인프라는 IaC(Infrastructure as Code) 툴인 [AWS CDK](https://github.com/kyopark2014/technical-summary/blob/main/cdk-introduction.md)를 이용해 구성합니다. 

## 문제 정의
