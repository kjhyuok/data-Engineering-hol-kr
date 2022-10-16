# Lab: Athena and QuickSight

## 소개<br>
Amazon Athena로 DataLake의 데이터에 ad-hoc query를 실행할 수 있습니다.<br>
Amazon QuickSight는 import한 데이터의 시각화 기능을 담당합니다.

## 시작하기 전에
Ingestiong with DMS와 Transforming data with Glue ETF 랩을 마치십시오

## 랩의 목표
1. Amazon Athena로 데이터에 query를 실행하고 view를 생성한다
2. Athena Workgroups to Control Query Access and Costs
3. Amazon QuickSight로 대시보드를 만든다

## Query Data with Amazon Athena
#### 1. AWS 콘솔창에서 Athena 검색
![AWS 콘솔](../images/aq/aq-1.png)

<details>
<summary> <em>Athena 사용이 처음이라면, 숨겨진 항목들을 수행하십시오 </em></summary>

1. Get Started 클릭
![AWS 콘솔](../images/aq/aq-athena-start.png)
2. 상단의 'set up a query result location in Amazon S3' 클릭
![AWS 콘솔](../images/aq/aq-setups3.png)
3. <b>Query result location</b>aq-필드의 팝업 윈도우에서 Select 아이콘 클릭.<br> dmslabs3bucket (e.g: dmslab-student-dmslabs3bucket-xg1hdyq60ibs) 선택 후, <b>Select</b> 버튼 선택
![AWS 콘솔](../images/aq/aq-selects3.png)
<br></br>
4. S3 위치 끝에 <b>athenaquery/</b> 추가 (끝에 "/"를 꼭 넣어주세요!). Save 클릭 <br>
![AWS 콘솔](../images/aq/aq-setting.png)
</details>

#### 2. <b>Query Editor</b> 에서 최근 생성한 데이터베이스 선택 e.g.,"<b>ticketdata</b>"
#### 3. "<b>parquet_sporting_event_ticket</b>" 테이블을 선택. 주의: id, sporting_event_id, ticketholder_id의 타입이 <b>double</b> 이어야 합니다.<br>
![AWS 콘솔](../images/aq/aq-queryeditor.png)<br></br>
이제 parquet_sporting_event, parquet_sport_team, parquet_sport_location 테이블을 사용한 query를 실행해볼 것 입니다.
#### 4. 다음 SQL문을 New Query 1 탭에 복사한 후 <b>Run Query</b> 클릭
``` SQL
SELECT
e.id AS event_id,
e.sport_type_name AS sport,
e.start_date_time AS event_date_time,
h.name AS home_team,
a.name AS away_team,
l.name AS location,
l.city
FROM parquet_sporting_event e,
parquet_sport_team h,
parquet_sport_team a,
parquet_sport_location l
WHERE
e.home_team_id = h.id
AND e.away_team_id = a.id
AND e.location_id = l.id;
```
Query창 아래에 결과가 보입니다
![AWS 콘솔](../images/aq/aq-sql1.png)
#### 5. <b>Create - Create view from query</b> 를 클릭해 Create view 창 실행
#### 6. Name에 sporting_event_info를 입력하고 <b>Create</b> 클릭
![AWS 콘솔](../images/aq/aq-view1.png)<br></br>
생성된 view가 아래와 같이 보입니다
![AWS 콘솔](../images/aq/aq-view1result.png)<br></br>
#### 7. 다음 SQL문을 <b>New Query 3</b>탭에 입력
``` sql
SELECT t.id AS ticket_id,
e.event_id,
e.sport,
e.event_date_time,
e.home_team,
e.away_team,
e.location,
e.city,
t.seat_level,
t.seat_section,
t.seat_row,
t.seat,
t.ticket_price,
p.full_name AS ticketholder
FROM sporting_event_info e,
parquet_sporting_event_ticket t,
parquet_person p
WHERE
t.sporting_event_id = e.event_id
AND t.ticketholder_id = p.id
```
![AWS 콘솔](../images/aq/aq-sql2.png)
#### 8. <b> Save as </b> 클릭 후, Name : create_view_sporting_event_ticket_info Description에 임의 내용을 입력 후 Save 클릭
![AWS 콘솔](../images/aq/aq-view2.png)<br></br>
Query Editor창에서 Query 이름이 바뀐 것을 확인할 수 있습니다.
<b>Run Query</b> 클릭
![AWS 콘솔](../images/aq/aq-runquery.png)
Query창 아래에 결과가 보입니다
![AWS 콘솔](../images/aq/aq-runqueryresult.png)
#### 9. <b>Create - Create view from query</b> 클릭
#### 10. Create view창에서 Name : <b>sporting_event_ticket_info</b> 입력 후 <b>Create</b> 클릭
![AWS 콘솔](../images/aq/aq-createview-seti.png)
#### 11. 다음 SQL문을 New Query 4 탭에 입력
``` sql
SELECT
sport,
count(distinct location) as locations,
count(distinct event_id) as events,
count(*) as tickets,
avg(ticket_price) as avg_ticket_price
FROM sporting_event_ticket_info
GROUP BY 1
ORDER BY 1;
```
<b>Save as</b> 클릭 후 Name : <b>analytics_sporting_event_ticket_info</b>, Description에 임의 내용 입력 후, <b>Save</b> 클릭
![AWS 콘솔](../images/aq/aq-save-aseti.png)
<br></br>
New Query 4의 이름이 바뀐 것을 확인할 수 있습니다.<br>
<b>Run Query</b> 클릭
<br></br>
![AWS 콘솔](../images/aq/aq-aseti-runquery.png)
<br></br>약 5초 후 2개 결과값이 리턴됩니다.<br> 1.59GB짜리 CSV파일이었던 데이터가 parquet 전환 뒤, 25MB로 축소되어 스캔됩니다.
![AWS 콘솔](../images/aq/aq-result-aseti.png)
<br></br>
query를 저장하면 실행결과들이 구분되어 저장됩니다. 그렇지 않을시 query 결과가 저장되는 S3버킷내 "Unsaved" 폴더에 저장되는데 S3버킷에 들어가보면 아래와 같이 확인해 볼 수 있습니다.
![AWS 콘솔](../images/aq/aq-s3.png)

다음 [4-2:QuickSight](../detail/4-2:CreateQuickSightDashboard.md)에서 QuickSight 대시보드 생성 실습을 시작해 봅니다.🤗
