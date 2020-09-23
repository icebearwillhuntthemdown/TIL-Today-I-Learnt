# SQL case when

SQL에서도 case when 구문을 넣어서 분기할 수 있다. case는 end로 닫고, 리턴값은 가상 컬럼이 되고 일반 컬럼처럼 alias를 쓸 수도 있다. 
```sql
select 
case 
    when count(1) > 0 then true
    else false
    end as existence
from users a
where 1 = 1
and a.user_id = #{userID};
```
위는 입력받은 userId의 중복 여부를 확인하는 쿼리다. case when 구문의 리턴값에 existence라는 alias를 붙였다. 해당 테이블에 userId와 일치하는 데이터가 있다면 true, 없다면 false를 리턴한다. count(1)은 count(*)와 같다.

```sql
select user_name, city, country
from users
order by
(case 
    when city is null then country
    else city
end);
```
위는 order by 절에서 case when을 사용했다. city가 Null일 때는 country를, null이 아닐 때는 city를 기준으로 정렬한다.
