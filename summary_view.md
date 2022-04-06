# view
- 가상의 테이블이다. (임시적), 실제 데이터를 저장하고 있는 것은 아니다.
- 특정 데이터를 모아서 view에 모아서 테이블 처럼 사용할 수 있다.
- 한번 생성 된 view는 수정과 인덱스 설정이 불가능 하다.
- view를 사용하여 쿼리를 단순하게 만들 수 있다. 

```sql
CREATE VIEW <뷰이름> AS
(QUERY)
```

### 예시
- world 데이터베이스에 coutry 테이블에서 국가코드와 국가이름이 있는 view 생성

```sql
CREATE VIEW country_code_name AS
SELECT code, name
FROM country ;
```
![view_1.png](./images/view_1.png)

![view_2.png](./images/view_2.png)

#### city 테이블과 country_code_name view를 합하기
- city 테이블에는 없는 국가의 이름 데이터를 하나의 테이블에서 볼 수 있다.

```sql
SELECT *
FROM city
JOIN country_code_name
ON city.countrycode = country_code_name.code ; 
```

![view_3.png](./images/view_3.png)


#### city + view 에서 도시인구가 5백만 이상인 데이터 조회
- 기존 테이블과 view를 합한 결과물은 임시적인 테이블과 같다.
- 이 결과물에서 바로 특정 조건으로 데이터 조회를 할 수 있다.
- view를 사용하지 않았으면 city 테이블과 country 테이블을 subquery 등의 다른 방법을 사용해야 한다.

```sql
SELECT city.name, district, population, country_code_name.name, country_code_name.code
FROM city
JOIN country_code_name
ON city.countrycode = country_code_name.code
WHERE population >= 5000000
ORDER BY population DESC ;
```

![view_4.png](./images/view_4.png)





