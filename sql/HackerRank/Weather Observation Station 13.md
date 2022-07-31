## Weather Observation Station 13

### Problem

![image](https://user-images.githubusercontent.com/84497369/182012105-d2cb55b0-b51a-4574-8579-8c99aca4cdb7.png)

Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38.7880 and less than 137.23345. <br> 
Truncate your answer to  decimal places.

### Answer

```sql
SELECT TRUNCATE(SUM(LAT_N),4)
FROM station
WHERE 38.7880 < LAT_N 
AND LAT_N < 137.2345
```

- greater than : 초과
- less than : 미만
- Truncate : 절삭 문법 ! 
