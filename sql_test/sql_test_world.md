# MySQL Test
- world 데이터 베이스를 사용한 코딩 문제를 풀어 보았다.
- 테이블과 컬럼
    - city
        - id, name, countrycode, district, population
    - country
        - code, name, continent, region, surfacearea, indepyear, population, lifeexpectance,
	- gnp, gnpold, localname, govermentform, headofstate, capital, code2
    - countrylanguage
        - countrycode, language, isofficial, percentage


### quiz 1
- country 테이블에서 중복을 제거한 continent 조회

```sql
SELECT DISTINCT(continent)
FROM country ;
```













