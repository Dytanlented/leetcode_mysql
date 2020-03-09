### Algorithm

1. Use LIMIT and OFFSET.
2. Use IFNULL() to avoid wrong answer in situation where there is only one record.


### Solutions

```sql
SELECT
    IFNULL(
        (SELECT DISTINCT Salary
        FROM Employee
        ORDER BY Salary DESC
        LIMIT 1 OFFSET 1),
        NULL) AS SecondHighestSalary
```