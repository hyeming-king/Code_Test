## Weather Observation Station 2

### Problem
Query the following two values from the STATION table:

1. The sum of all values in LAT_N rounded to a scale of  decimal places.
2. The sum of all values in LONG_W rounded to a scale of  decimal places.

![image](https://user-images.githubusercontent.com/84497369/181878871-9bfead50-f038-4ab4-80f4-082e42845d24.png)



<br>

### Answer

````sql
SELECT ROUND(SUM(LAT_N),2) AS lat,
       ROUND(SUM(LONG_W),2) AS lon
FROM STATION
````
