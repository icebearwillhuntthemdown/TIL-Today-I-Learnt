# Where
- conditions to filter the rows returned from the `SELECT` clause
- The condition must evaluate to true, false, or unknwon
- The query returns only rows that satisfy the condition in the `WHERE` clause
- Only rows that cause the condition evaluates to true will be included in the result set.

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

### IN
list of values

### BETWEEN
range of values

