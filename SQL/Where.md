# Where
- conditions to filter the rows returned from the `SELECT` clause
- The condition must evaluate to true, false, or unknwon
- The query returns only rows that satisfy the condition in the `WHERE` clause
- Only rows that cause the condition evaluates to true will be included in the result set.


### IN & ANY
- list of values
- 조건절에 서브쿼리에서 추출한 값의 리스트 활용
- IN과 ANY는 호환 가능하며, ANY 대신 SOME을 쓸 수 도 있다

```sql
// IN
    select ...columns
      from table_a a
     where column_a in (
                        select column_b
                          from table_b b
                         where b.id = a.id
)

// ANY (SOME)
    select ...columns
      from table_a a
     where column_a = any (
                        select column_b
                          from table_b b
                         where b.id = a.id
)
```



### BETWEEN
range of values  


### Like
- % : matches any sequence of **zero or more** charaters
- _ : matches any **single** charater
```sql
    'foo' LIKE 'foo', -- true
    'foo' LIKE 'f%', -- true
    'foo' LIKE '_o_', -- true
    'bar' LIKE 'b_'; -- false
```

### ILIKE
`ILIKE` works like `LIKE` but it's case-insensitive

### Operators
- ~~ : LIKE
- ~~* : ILIKE
- !~~ : NOT LIKE
- !~~* : NOT ILIKE
