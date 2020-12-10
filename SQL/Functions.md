# Functions
## array_agg()
- syntax  
`ARRAY_AGG ( expression [ORDER BY [sort_expression {ASC | DESC} ]`
- group by와 함께 쓰이며 배열을 리턴
```sql
select title
     , ARRAY_AGG (
        first_name || ' ' || last_name
        order by first_name
        ) actors
  from film
group by title
order by title
```

## string_agg
- syntax  
`STRING_AGG ( expression, separator [order_by_clause] )`
- 구분자를 포함해 이어 붙인 스트링을 리턴
```sql
select title
     , STRING_AGG (
        a.first_name || ' ' || a.last_name
        ','
        ORDER BY a.first_name, a.last_name
        ) actors
  from film f
  inner join actors a using (actor_id)
group by f.title   
```

## LENGTH()
- syntax  
`LENGTH(string` 
- 해당 스트링의 글자 수를 리턴
