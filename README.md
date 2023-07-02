# README

## AWS기반 데이터레이크 구성을 위한 Data Engineering Immersion Day

기존 AWS의 Workshop인 [**Data Engineering Immersion Day**](https://catalog.us-east-1.prod.workshops.aws/workshops/976050cc-0606-4b23-b49f-ca7b8ac4b153/en-US/)을 한글화 하고, 실습자에게 필요한 부분만 구성합니다.\
본 Workshop은 3\~4시간 정도 소요되며, 활용되는 AWS Resource 목록은 다음과 같습니다.

* [AWS DMS](https://aws.amazon.com/ko/dms/), [Amazon S3](https://aws.amazon.com/ko/s3/), [Amazon Glue](https://aws.amazon.com/ko/glue/), [Amazon Athena](https://aws.amazon.com/ko/athena/), [Amazon QuickSight](https://aws.amazon.com/ko/quicksight/)

## Data Engineering Immersion Day 개요

![대체 텍스트](images/intro.png)

### Data Engineering Immersion Day?

_Data Engineering Immersion Day_에서는 AWS의 데이터 레이크 관점에서의 데이터 수집, 처리, 쿼리 및 소비에 초점을 맞춘 실습을 수행 합니다.\
본 Immersion Day에서는 여러분의 IDC에 위치했다고 가정한 원본 데이터베이스의 수집을 위한 [AWS DMS(데이터 마이그레이션 서비스)](https://docs.aws.amazon.com/ko\_kr/dms/latest/userguide/Welcome.html), 데이터 카탈로그 및 실행을 위한 [AWS GLUE](https://docs.aws.amazon.com/ko\_kr/glue/latest/dg/what-is-glue.html), 데이터 레이크를 위해 S3를 쿼리하고 뷰테이블을 생성하는 [AMAZON Athena](https://docs.aws.amazon.com/ko\_kr/athena/latest/ug/what-is.html), 최종적으로 정제된 데이터의 시각화를 위한 [AMAZON QuickSight](https://aws.amazon.com/ko/quicksight/) 등 AWS 분석 서비스를 직접 이용할 수 있는 경험을 제공합니다.\
본 Immersion Day를 수행하면 클라우드 네이티브 및 서버리스 데이터 레이크를 구축하는 데 도움이 될 수 있습니다.\
\
이 Immersion Day는 크게 3가지의 단계로 이루어져 있으며, 사전에 2개의 단계를 확인 합니다.\
[_**0.Introduction**_](detail/introduction.md) 에서는 단계별 실습에서 진행하는 각 Architecture에 대해 기술합니다.\
[_**1.Lab: Setting Lab Account**_](detail/1.lab-settinglabaccount.md) 에서는 AWS에서 제공하는 실습용 Account를 Setting하고 [AWS Web Console](https://signin.aws.amazon.com/signin?redirect\_uri=https%3A%2F%2Fconsole.aws.amazon.com%2Fconsole%2Fhome%3FhashArgs%3D%2523%26isauthcode%3Dtrue%26state%3DhashArgsFromTB\_us-west-2\_fb2cdefd242e800d\&client\_id=arn%3Aaws%3Asignin%3A%3A%3Aconsole%2Fcanvas\&forceMobileApp=0\&code\_challenge=\_L\_92-86xjANu4YyDZwXJj--tPwQK81v471vY05aM08\&code\_challenge\_method=SHA-256)에 접근하여 실습을 할 수 있는 환경을 준비합니다.

본 Workshop에 오류가 있거나 AWS Console ui가 업데이트 되어 맞지 않는 부분이 있으면 작성자에게 메일 부탁드립니다.\
kjhyuok@amazon.com(JongHyuok, Kim)

***

#### [0.Introduction](detail/introduction.md)

#### [1.Lab: Setting Lab Account](detail/1.lab-settinglabaccount.md)

#### [2.Lab: Ingestion with DMS](detail/2.labingestionwithdms/)

#### [3.Lab: Transforming data with Glue](detail/3.labtransformingdatawithglue/)

#### [4.Lab: Query and Visualize](detail/4.lab-querynvisualize/)
