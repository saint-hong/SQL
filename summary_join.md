# join
- 여러개의 테이블을 합해준다. 
- 기본적으로 inner join, left join, right join, outer join 이 있다.
- 행을 기준으로 데이터를 합한다.
- 헷갈리는 부분 :

```
from 에서 어떤 테이블을 설정하느냐에 따라서 left, right join 의 출력이 달라진다.
```
![join.png](./images/join.png)

## database 생성

```sql
create database example ;
```

## database 선택

```sql
use example ;
```

## table 생성
- film 테이블
- film_id, title, release_year 컬럼

```sql
create table film_table(
	film_id INT,
	title Varchar(20) NOT NULL,
	release_year DATE) ;
```

- actor 테이블
- film_id, name, age 컬럼

```sql
create table actor_table(
	film_id INT,
	name Varchar(20) NOT NULL,
	age INT(3) DEFAULT '30') ;
```

## 테이블 별 데이터 생성
- film 테이블에 영화 데이터 넣기

```sql
insert into film_table(film_id, title, release_year)
values (101, "no time to die", "2020-01-01"),
(102, "voice", "2017-06-21"),
(103, "venom", "2010-05-15"),
(105, "dune", "2009-09-09") ;
```

- actor 테이블에 배우 데이터 넣기

```sql
insert into actor_table(film_id, name, age)
values (101, "daniel craig", 50),
(102, "byunyohan", 35),
(103, "tom hardy", 46),
(103, "naomi harris", 28) ;
```

## 데이터 확인
- actor 테이블 확인

```sql
select *
from actor_table ;
```

![join_1.PNG](./images/join_1.PNG)

- film 테이블 확인

```sql
select *
from film_table ;
```

![join_2.PNG](./images/join_2.PNG)

## join
- 기본적으로 inner join 에 해당한다.
- film 테이블과 actor 테이블을 join
- 공통된 컬럼의 값을 기준으로 두 테이블에서 값을 가져온다. (교집합)
- film_id 가 공통값이므로 이것을 기준으로 일치하는 값에 해당하는 행전부를 합해서 보여준다.

```sql
select film_table.film_id, film_table.title, film_table.release_year,
	actor_table.name, actor_table.age
from film_table
join actor_table
on film_table.film_id = actor_table.film_id ;
```

![join_join.PNG](./images/join_join.PNG)

### left join, right join 
- left join 과 right join 은 두개의 테이블 중에서 left, right로 정한 테이블을 기준으로 합한다.
- 기준으로 정한 테이블의 모든 값을 불러오고, 다른 테이블이 여기에 일치하지 않을 경우 null 값으로 출력된다.
- 중요한점 : 
```
왼쪽에 오는 테이블을 기준으로 하며, from 에서 정한다.
```
- from 에 어떤 테이블을 놓느냐에 따라서 left, right join 의 기준이 달라지게 된다.

#### left join
- 왼쪽 테이블로 film_table 을 설정한 경우
- film_table 이 왼쪽으로 설정되었고, left join actor_table 에서 왼쪽 테이블이 기준이 된다.
- 따라서 film_table 의 모든 값이 출력되고, 여기에 일치하지 않는 actor_table 의 값은 null 로 출력된다.

```sql
select film_table.film_id, film_table.title, film_table.release_year,
actor_table.name, actor_table.age
from film_table
left join actor_table
on film_table.film_id = actor_table.film_id ;
```

![join_left.PNG](./images/join_left.PNG)

#### rignt join
- film_table 이 왼쪽으로 설정되었고, right join actor_table 에서 오른쪽 테이블이 기준이 된다.
- 따라서 actor_table 의 모든 값이 출력되고, 여기에 일치하지 않는 film_table 의 값은 제외된다. 

```sql
select film_table.film_id, film_table.title, film_table.release_year,
actor_table.name, actor_table.age
from film_table
right join actor_table
on film_table.film_id = actor_table.film_id ;
```

![join_righ.PNG](./images/join_right.PNG)

#### 왼쪽 테이블로 actor_table 을 설정한 경우
- from film_table 을 설정한 경우와 반대로 출력된다. 
- left join
- from film_table 의 right_join actor_table 과 같은 결과가 출력된다.

```sql
select film_table.film_id, film_table.title, film_table.release_year,
actor_table.name, actor_table.age
from actor_table
left join film_table
on film_table.film_id = actor_table.film_id ;
```

![join_left_2.PNV](./images/join_left_2.PNG)

#### 오른쪽 테이블로 film_table 을 설정한 경우
- right join
- from film_table 의 left join actor_table 과 같은 결과가 출력된다.

```sql
select film_table.film_id, film_table.title, film_table.release_year,
actor_table.name, actor_table.age
from actor_table
right join film_table
on film_table.film_id = actor_table.film_id ;
```

![join_right_2.PNG](./images/join_right_2.PNG)

### outer join
- union 을 사용하여 두 테이블의 모든 데이터를 합하여 보여준다.
- left join 과 right join 을 union 으로 합한다.
- 단 from 으로 설정한 테이블이 같아야 한다.

```sql
select film_table.film_id, film_table.title, film_table.release_year,
actor_table.name, actor_table.age
from film_table
left join actor_table
on film_table.film_id = actor_table.film_id
union
select film_table.film_id, film_table.title, film_table.release_year,
actor_table.name, actor_table.age
from film_table
right join actor_table
on film_table.film_id = actor_table.film_id ;
```

![join_outer.PNG](./images/join_outer.PNG)
