## Weather Observation Station 18

### Problem

Consider P1(a,b) and P2(c,d) to be two points on a 2D plane.

- a happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
- b happens to equal the minimum value in Western Longitude (LONG_W in STATION).
- c happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
- d happens to equal the maximum value in Western Longitude (LONG_W in STATION).

Query the Manhattan Distance between points P1(a,b) and P2(c,d) and round it to a scale of  decimal places.


<br>

### Answer
````sql
SELECT ABS(a-c)+ABS(b-d)
FROM (SELECT ROUND(MIN(LAT_N),4) AS a
        , ROUND(MIN(LONG_W),4) AS b
        , ROUND(MAX(LAT_N),4) AS c
        , ROUND(MAX(LONG_W),4) AS d
      FROM station) AS p
````
**< Manhattan Distance >**
- p1(x1, y1) , p2(x2, y2)
- 거리 : |x 1 - x 2 | + |y 1 - y 2 |
<img width="668" alt="image" src="https://user-images.githubusercontent.com/84497369/181879936-7feac19c-27ae-4bfb-9336-6e0e17282071.png">
