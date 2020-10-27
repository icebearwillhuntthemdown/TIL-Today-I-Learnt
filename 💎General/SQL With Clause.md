# With Clause
`With`절을 쓰면 가상의 쿼리에 이름을 붙여서 메인 쿼리에서 참조할 수 있다. CTE라고도 하는데, Common Table Expression의 준말이다. 
<br/><br/>

## Syntax
```SQL
  WITH expression_name [(column_name [, ...n])]
    AS (CTE_query_definition)
SELECT [column1, column2, ...]
  FROM expression_name
```
<br/><br/>

## Example
```SQL
  WITH tempTable(averageSalary)
    AS (
        SELECT avg(Salary) 
          FROM Employee
       ),
SELECT EmpId
     , EmpName
     , Salary
  FROM Employee E
 WHERE E.Salary > tempTable.averageSalary;
```
<br/><br/>

## Reference
- https://www.sqlshack.com/sql-server-common-table-expressions-cte/
