# Big Query 
- 변성윤 님의 <빅쿼리의 모든 것> - 입문편 을 읽고 요약 정리 함
- 데이터 저장소 : data base 라고 부름, MYSQL, MSSQL, BigQuery 등으로 부르기도함.
- big query는 데이터 분석을 할 때 장점이 있는 데이터 저장소
- SQL은 RDBMS에서 데이터를 추출할 때 사용하는 문법
- Google Cloud Platform의 data warehouse의 이름 : BigQuery 
   - sql을 통해 데이터를 추출할 수 있는 공간

### Big Query의 장점
- 난이도 : sql 기반으로 데이터를 추출할 수 있다.
- 속도 : big query는 index개념이 없어서 속도가 느려지지 않는다.
   - 다른 데이터베이스는 index 또는 서버 성능에 따라서 속도가 느리기도하다.
- firebase를 사용할 경우 앱 데이터를 쉽게 추출할 수 있다.
   - 사용기기, 위치(시 단위까지 표현), os 버전, 이벤트 행동 데이터 추출 가능
   - 안드로이드의 경우에는 app_remove까지 확인 가능하다.
   - firebase : 모바일 웹 애플리케이션 개발 플랫폼, 애플리케이션을 운영하고 분석할 수 있는 기능
- 서버를 따로 구축하거나 관리가 필요없다.

### Big Query의 2가지 문법
- Legacy SQL : 과거에 주로 사용하던 문법
- Standard SQL : 최근에 주로 사용하는 문법 (이 문법으로 사용한다)
- BigQuery StandardSQL + 검색어 : 이런식으로 검색한다. 

### google cloude 빅쿼리 가격정책
- 사용한만큼만 지불 : $5 / TB
- 구독 : $1,700 / month

### Big Query 는 어떻게 사용될까?
- 기획, 마케팅, 신사업 등 다양한 팀에서 모두 "데이터 기반의 의사 결정을 진행" 하는 경우
   - 각자 팀에서 스스로 쿼리를 날려서 빅쿼리에서 필요한 데이터를 추출한다.
- 가설을 설정한 후 , 데이터를 통해서 가설이 진짜 맞는지 확인 할 수 있다.
- 머신러닝용 Feature 생성 할 수 있다. 

### 여러가지 데이터의 종류
- 현재 BigQuery에 어떤 데이터가 쌓이고 있는지 점검하기

#### 1) 앱로그 데이터
- 유저가 앱에 들어와서 회워가입을 하거나, 페이지 확인, 컨텐츠 확인 등의 액션 데이터
- 흐름을 알 수 있는 데이터
- firebase에서 BigQuery로 데이터를 저장한다.

#### 2) 결제 데이터
- 결제가 있는 서비스라면 최종 결재 금액 데이터

#### 3) 유저데이터
- 유저의 정보 : 성별, 연령대 등

#### 4) 공공데이터 
- 날씨, 위치 좌표 등

### BigQuery Console 구글 플랫폼의 빅쿼리
- 구글 클라우드 플랫폼 사용 방법 (버젼 바뀜, 메뉴위치가 바뀌었으나 거의 비슷함)
   - 패캠에서는 하이디SQL 사용
- 데이터추가하기 -> 공개 데이터 세트 이용 : 공개 된 데이터 많음
- 몇가지 메뉴 설명
   - 전송 transfer : 빅데이터를 다른 곳에서 현재 구글 클라우드 빅쿼리로 옮김
   - 예약된 쿼리 scheduled queries : 특정 시간대에 반복적으로 쿼리 실행
   - BI Engine : 데이터를 시각화 해주는 도구

# SQL 이해하기
- SQL : Structured Query Langauge
- RDBMS의 데이터를 관리하기 위해 설계된 특수 목적의 프로그래밍 언어
   - RDBMS : 데이터를 관계로 표현해주는 기능, 마치 엑셀과 유사하다.

### SQL 문법 
- 빅쿼리에 있는 것
   - 데이터 선택 : SELECT 
   - 데이터 조작 (DML : data mainpulation language) : INSERT, UPDATE, DELETE
   - 데이터 정의 (DDL : data definition language) : CREATE, ALTER, DROP
- 빅쿼리에 없는 것
   - 데이터 제어 (DCL : data control language) : 

### SQL 실습 (1) - 공개 데이터 세트에서 city bike 데이터 사용
- SQL 문법은 study-mysql 레포지토리에 정리

### SQL 실습 - 데이터 시각화
- 구글 스프레드시트 사용
   - 쿼리를 날린다 (전송 한 후) -> 구글 스프레드시트로 저장한다 -> 스프레드시트로 시각화한다.
   - 엑셀과 유사하다. 공유가 편하고 쉽다. 시각화 종류가 적고, 16,000 행까지만 가능하다.
- 태블로 사용
   - Tableau에 BigQuery를 연결해서 시각화 한다.
   - 시각화를 쉽게 할 수 있다. 유료이다.
   - tableau webinar 검색하면 다양한 자료 나온다. 
- 파이썬 사용
   - 쿼리를 날린다 -> 데이터를 내 컴퓨터에 저장해서 python으로 시각화 한다. 
   - matplotlib, seaborn, plotly 시각화 라이브러리 사용
   - 파이썬과 시각화 라이브러리에 능숙해야 사용할 수 있다.
- data studio를 사용해서 시각화
   - 쿼리 결과에서 클릭한번 하면 진행이 가능하다.
   - 스프레드 시트 상위 호환 가능
- 여러가지 방법이 존재한다. 

### SQL 실습 (2) - 공개 데이터 세트에서 city bike 데이터 사용
- SQL 문법은 study-mysql 레포지토리에 정리

### 빅쿼리 심화 

### SQL 실습 (3) - 공개 데이터 세트에서 city bike 데이터 사용
- SQL 문법은 study-mysql 레포지토리에 정리

### DML Query
- 데이터를 조작하는 쿼리 , data mainpulation language : 거의 사용안하는 것 같다.
- 빅쿼리 테이블에 데이터를 업데이트, 삽입, 삭제할 수 있는 기능
- insert, update, delete

# Big Query : 스케줄 쿼리
- 특정 쿼리를 매일 특정시간에 돌려야 할 경우
- 개발자의 경우
   - 인스턴스 생성하고 crontab 등록하여 사용
   - AWS Lambda + CloudWatch Event 사용
   - Airflow 인스턴스 띄우고 관리
- 마케터, 기획자의 경우 : 구글 클라우드 플랫폼 스케줄 설명 - 구글링해서 해보기
   - 구글 클라우드 플랫폼에서 스케줄 쿼리 사용
   - bigquery data transfer api 사용 설정하여 사용 가능

# Big Query : Table 생성하기 - 데이터 불러오기
- 프로젝트에 하위 노드
   - 여러가지 데이터 세트 있음
   - 데이터 세트 하위 노드 -> 여러가지 테이블 있음
   - 데이터 세트의 메뉴 점3개 누르면 테이블 만들기 있음
- 테이블 만들기에서 소스 누르면 생성 방식나옴
   - 여기에서 로컬에 있는 데이터 불러 와서 테이블을 만들 수 있음. 
   - 기본적인 테이블 환경 설정 가능
   - 빈테이블
   - google cloud storage : 가장 많이 사용하는 방법 중 하나
   - 업로드 : 로컬에서 데이터 업로드
   - 드라이브
   - google bigtabel
   - amazon s3

# Big Query : 쿼리 결과 다운로드 하기 - 데이터 추출하기
- 구글 클라우드 플랫폼 빅쿼리에서 내보내기 메뉴
   - 데이터 스튜디오로 탐색
   - GCS로 내보내기 : 구글 스토리지로 내보내기
   - DLP로 스캔 : 확인 해볼 것
- 16,000 행 이내일 경우 : CSV 로컬파일로 저장, 구글 스프레드 시트로 저장
- 1GB 이하일 경우 (행상관없음) : CSV 구글 드라이브에 저장, json 구글 드라이브에 저장
- 1GB 초과 16,000행 초과 : Big Query 테이블로 저장 -> 구글 스토리지에 저장
- 파이썬을 사용할 수 있는 경우 : pd.read_gbq 로 쿼기 결과를 메모리에 저장
 
### 구글 스토리지에 저장하기 
- 1GB 초과 또는 16,000행 초과시에 사용하면 좋다.
- 빅쿼리 테이블로 저장한 후 구글 스토리지에 저장하기
- 구글 스토리지에 버킷이 생성 되어 있어야 함.
   - 버킷 만들기 -> 이름 만들기 -> region 설정 서버 설정인듯
- 내보내기 메뉴 -> GCS로 내보내기
   - GCS 위치 -> 찾아보기 -> 구글 스토리지에 생성된 버킷이름 뜬다
   - 새 버킷 만들기로 바로 데이터를 저장할 수 있다. 
   - 버킷 선택하고 파일명 입력하고 선택 누르면 최종 저장화면 나옴
   - example_0319/city_bike_share_result
   - 내보내기 형식 : CSV, JSON, Avro, ParQuet
   - 압축 : Gzip
   - 저장 누르기 : 구글 스토리지에 가서 저장 됐는지 확인하기 (잘 저장 됐다.)

### 파이썬을 사용하여 로컬 메모리에 저장하기
- 사용방법 확인하기 : 인증받고, 키설정 해야하는 듯
- pd.read_gbq 사용해야함

# Firebase Log
- 앱 관리 프로그램인 firebase에서 데이터를 추출하고 다루는 방법
   - firebase 앱 데이터는 형태가 보기 어렵게 되어 있다.
   - 이러한 데이터를 query 를 사용하여 필요한 데이터를 추출한다.
   - firebase의 고객센터에 자동으로 수집되는 데이터에 대한 정보있음
- 즉 내가 알고 싶은 데이터가 아닌 것들을 제외 시키고 필요한 것만 보면 됨.
- firebase 앱 데이터는 가공을 해서 사용하는 것이 좋다. 비용 문제 발생.

# Data Pipeline
- 데이터 파이프라인 구조 설명
- 로우 데이터를 어떻게 가져오느냐에 따라서 비용이 달라질 수 있다.
- 로우 데이터를 특정한 양식으로 필터링하는 반복적인 업무를 airflow를 사용
- 데이터 관리 팀에서 로우데이터를 사용할 수 있는 데이터로 관리
   - 각 팀별로 이 데이터를 사용
- 데이터 베이스 마다 데이터 파이프라인 구조가 다르다.
   - AWS
   - Pub/Sub 
   - Streaming 실시간??
   - Kafka
   - airflow

# Python에서 bigquery 사용하기

### 서비스키를 사용하여 빅쿼리 불러오기

```python
import pandas as pd

query = "SELECT * FROM 'dataset.table"
df = pd.read_gbq(query=query, project_id = "project_id",
                       dialect='standard', private_key='your json key path'
```

### user_account 인증해서 빅쿼리 불러오기
- 서비스키를 사용하지 않음
- 서비스키 발급하고 권한을 주는 일을 GCP IAM으로 관리가 가능하다.

```python
pip install pydata_google_auth
```
```python
import pandas as pd
import pydata_google_auth

SCOPES = [
	'https://www.googleapis.com/auth/cloud-platform',
	'https://www.googleapis.com/auth/drive',
	'https://www.googleapis.com/auth/bigquery'
]

credentials = pydata_google_auth.get_user_credentials(SCOPES, auth_local_webserver=True)

query = "SELECT * FROM 'dataset.table'"
df = pd.read_gbq(query=query, project_id="profect_id", credentials=credentials)
```

### 빅쿼리에서 처리하기 어려운 것들을 python에서 하면 좋다
- bigquery 전처리 퍼포먼스 -> python 전처리 퍼포먼스

# Big Query : 데이터셋 공유하기
- 구글 클라우드 플랫폼 빅쿼리에서 데이터세트 공유
- 공유 버튼 누르면 
   - 데이터의 리소스 권한 상태가 나옴
   - 상속된 권한 표시에서 데이터 공유에 관한 권한을 설정 할 수 있음



