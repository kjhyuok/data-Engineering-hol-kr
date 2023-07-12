# Lab4-3: QuickSight 기능 둘러보기

## QuickSight 차트 생성

이 섹션에서 여러 타입의 차트를 만들어 보겠습니다

#### 1. *Fields list*에서 _ticket\_price_ 컬럼을 클릭

#### 2. *ticket\_price*필드의 expand icon을 클릭하고, 숫자를 달러값으로 표시하기 위해 _Show as Currency_ 선택

#### 3. 화면 왼쪽 상단에 있는 _Add_ 을 클릭 후, Add visual 할 수 있습니다.

* Data set 아래 Visual types 에서 Vertical bar chart 아이콘 선택
* 이 레이아웃은 X-axis 값이 필요합니다. Fields list에서, event\_date\_time를 선택하면 그래프가 업데이트됩니다.
* Value로 Fields list에서 ticket\_price 선택

![AWS 콘솔](../../images/qs-func/chart1.png)

#### 4. 대시보드에 필드를 드래그해 가져올 수도 있습니다. Field list에서 *seat_level*을 클릭하고 *Group/Color*박스로 드래그하세요.

![AWS 콘솔](../../images/qs-func/chart2.png)

차트 타입을 바꿔봅시다

#### 5. Visual types에서 _Clustered bar combo chart_ 선택

#### 6. Field list에서 *ticketholder*필드를 *Lines*박스로 드래그

#### 7. *Lines*박스에서, 드롭다운박스 클릭해 Aggregate을 위해 *Aggregate: Count Distinc*선택. 오른쪽에서 y-axis에 업데이트를 확인할 수 있습니다.

![AWS 콘솔](../../images/qs-func/chart3.png)

#### 8. 왼쪽 탭 섹션에서 *insight*아이콘을 클릭해 간단한 인사이트 정보를 확인해볼 수 있습니다

![AWS 콘솔](../../images/qs-func/chart4.png)

### 다양한 차트 타입과 필드로 차트를 테스트해보세요!!

## QuickSight Parameters 생성

이 섹션에서는 대시보드값을 조정할 수 있는 파라미터들을 생성하고 filter에 할당해 보겠습니다

#### 1. 왼쪽 네비게이션 메뉴들에서, Parameters 선택

![AWS 콘솔](../../images/qs-func/parameter1.png)

#### 2. 새로운 파라미터 생성을 위해 _Create one_ 선택

#### 3. Name에 _EventForm_ 입력

#### 4. Data type에 _Datetime_ 선택

#### 5. Time granularity에 _Hour_ 선택

#### 6. Default value로 *event_date_time*의 범위에서 시작 날짜로 가능한 날짜 선택. 예) 2021-01-01 00:00

#### 7. _Create_ 클릭

![AWS 콘솔](../../images/qs-func/parameter2.png)

#### 8. 아래 속성들로 파라미터를 하나 더 생성

**- Name: EventTo**

**- Data type: Datetime**

**- Time granularity, Hour**

**- Default value로 *event_date_time*의 범위에서 종료 날짜로 가능한 날짜 선택. 예) 2022-01-01 00:00**

**- Create 클릭**

![AWS 콘솔](../../images/qs-func/parameter3.png)

#### 9. 다른 방법으로 _EventFrom_ 파라미터에서 _Add control_ 선택할 수도 있습니다.

![AWS 콘솔](../../images/qs-func/parameter4.png)

#### 10. Display name으로 Event From을 입력하고 Add 클릭

![AWS 콘솔](../../images/qs-func/parameter5.png)

#### 11. EventTo로 같은 작업을 반복하고 Display name은 _Event To_ 입력

![AWS 콘솔](../../images/qs-func/parameter6.png)

이제 위 차트에서 지정된 파라미터 조건에 따라 변경된 차트를 확인할 수 있습니다.

![AWS 콘솔](../../images/qs-func/parameter7.png)

## QuickSight Filter 생성

모든 Visual에 filter를 적용해 보겠습니다

#### 1. 왼쪽 네비게이션 메뉴에서 Filter 선택

#### 2. ADD FILTER를 클릭해 *event_date_time*필드에 대한 filter 추가

![AWS 콘솔](../../images/qs-func/filter1.png)

#### 3. 속성을 수정하기 위해 event_date_time(필터) 선택

![AWS 콘솔](../../images/qs-func/filter2.png)

#### 4. Filter type으로 *Date & Time range*와 *Between* 선택

#### 5. *Use Parameters* 옵션 선택 후 _Yes_ 클릭

#### 6. *Start date parameter*로 _EventFrom_ 선택

#### 7. *End date parameter*로 _EventTo_ 선택

#### 8. _Apply_ 클릭

![AWS 콘솔](../../images/qs-func/filter3.png)

Federated Query 기능이 궁금하시다면 다음 실습을 활용해주세요! [4-4:Federated Query](4-4-athenafederatedquery.md)
