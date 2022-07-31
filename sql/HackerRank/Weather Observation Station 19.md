## Weather Observation Station 19

### Problem
![image](https://user-images.githubusercontent.com/84497369/182013647-983e5b10-97d3-4599-bdb9-23e66efcc2ef.png)

Consider P1(a,b) and P2(c,d) to be two points on a 2D plane.

- a happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
- b happens to equal the minimum value in Western Longitude (LONG_W in STATION).
- c happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
- d happens to equal the maximum value in Western Longitude (LONG_W in STATION).

Query the  Euclidean Distance between points P1(a,b) and P2(c,d) and round it to a scale of decimal places.


- 유클리디안 거리 구하기

![image](https://user-images.githubusercontent.com/84497369/182013689-a0b4942c-270e-4b98-b949-1200412833ce.png)

<br>

### Answer
```sql
SELECT ROUND(SQRT(POW(a-c,2)+POW(b-d,2)),4)
FROM (SELECT ROUND(MIN(LAT_N),4) AS a
        , ROUND(MIN(LONG_W),4) AS b
        , ROUND(MAX(LAT_N),4) AS c
        , ROUND(MAX(LONG_W),4) AS d
        FROM STATION) s1
```        
  
  
- POW(a,b) : a의 b제곱 구하기
- SQRT(a) : a의 제곱근 구하기
  
  
