## Weather Observation Station 17
### Problem

Query the Western Longitude (LONG_W)where the smallest Northern Latitude (LAT_N) in STATION is greater than 38.7780.

Round your answer to  decimal places.

<img width="269" alt="image" src="https://user-images.githubusercontent.com/84497369/182370485-5db5cb23-07cd-467a-8239-cd769721ff57.png">



### Answer

문제를 해석하는 데 조금 어려웠었다. 영어공부의 중요성

- Latitude 가 38.7880보다 큰 제일 작은 값의 Longitude 를 구하라는 문제 


```sql
SELECT ROUND((LONG_W),4) 
FROM STATION
WHERE LAT_N > 38.7880
ORDER BY LAT_N
LIMIT 1

```
