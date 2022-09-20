# AWS기반 데이터레이크 구성을 위한 Data Engineering HoL

기존 [data-Engineering-hol](https://catalog.us-east-1.prod.workshops.aws/workshops/976050cc-0606-4b23-b49f-ca7b8ac4b153/en-US/)을 한글화 하고, 실습자에게 필요한 부분만 정리하여 구성합니다.

# Data Engineering Immersion Day 개요
![대체 텍스트](./images/intro.png)

## Data Engineering Immersion Day란?\
Data Engineering Imposition Day에서는 AWS의 데이터 레이크 관점에서의 데이터 수집, 공급, 탐색 및 소비에 초점을 맞춘 실습을 수행 합니다.\
본 HoL에서는 여러분의 IDC에 위치했다고 가정한 원본 데이터베이스의 수집을 위한 [AWS DMS(데이터 마이그레이션 서비스)](https://docs.aws.amazon.com/ko_kr/dms/latest/userguide/Welcome.html), 데이터 카탈로그 및 실행을 위한 [AWS GLUE](https://docs.aws.amazon.com/ko_kr/glue/latest/dg/what-is-glue.html), 데이터 레이크를 위해 S3를 쿼리하고 뷰테이블을 생성하는 [AMAZON Athena](https://docs.aws.amazon.com/ko_kr/athena/latest/ug/what-is.html), 최종적으로 정제된 데이터의 시각화를 위한 [AMAZON QuickSight](https://aws.amazon.com/ko/quicksight/) 등 AWS 분석 서비스를 직접 이용할 수 있는 경험을 제공합니다.\
본 Immersion Day를 수행하면 클라우드 네이티브 및 서버리스 데이터 레이크를 구축하는 데 도움이 될 수 있습니다.\
\
이 HoL은 크게 3가지의 단계로 이루어져 있으며, \
*0.Introduction*에서는 단계별 실습에서 진행하는 각 Architecture에 대해 기술합니다.\
*1.Lab: Setting Lab Account*에서는 AWS에서 제공하는 실습용 Account를 Setting하고 [AWS Web Console](https://signin.aws.amazon.com/signin?redirect_uri=https%3A%2F%2Fconsole.aws.amazon.com%2Fconsole%2Fhome%3FhashArgs%3D%2523%26isauthcode%3Dtrue%26state%3DhashArgsFromTB_us-west-2_fb2cdefd242e800d&client_id=arn%3Aaws%3Asignin%3A%3A%3Aconsole%2Fcanvas&forceMobileApp=0&code_challenge=_L_92-86xjANu4YyDZwXJj--tPwQK81v471vY05aM08&code_challenge_method=SHA-256)에 접근하여 실습을 할 수 있는 환경을 준비합니다.


### [0.Introduction](./detail/introduction.md)

### [1.Lab: Setting Lab Account](./detail/1.Lab:SettingLabAccount.md)

### [2.Lab: Ingestion with DMS](./detail/ingestion.md)

### [3.Lab: Transforming data with Glue](./detail/transformingdata.md)

### [4.Lab: Query and Visualize](./detail/queryandvisualize.md)

