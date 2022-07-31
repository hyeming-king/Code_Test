## Weather Observation Station 3

### Problem
Query a list of CITY names from STATION for cities that have an even ID number. <br>
Print the results in any order, but exclude duplicates from the answer.


### Answer


```sql
SELECT DISTINCT CITY
FROM STATION
WHERE id%2=0
```

**<나머지 구하기>**
- 오라클 : MOD(n.m)
- Mysql : n%m

