## Weather Observation Station 5
### Problem


Table : station
<img width="256" alt="image" src="https://user-images.githubusercontent.com/84497369/184073712-938af5b9-d835-433b-8501-9c430f165db9.png">

city 이름이 가장 적은 이름과, 긴 이름의 city와 길이를 출력하라


### Answer

  
```sql
SELECT CITY, LENGTH(CITY)
FROM station
ORDER BY LENGTH(CITY), CITY
LIMIT 1;

SELECT CITY, LENGTH(CITY)
FROM STATION
ORDER BY LENGTH(CITY) desc, CITY
LIMIT 1;
```

문제를 쉽게 풀 수 있는 방법이 있는 데도 -> 나눠서 쿼리문 여러개 짜기
숴브쿼리로 짜려고 해서 너무 어려웠다.

간단하고 쉽게 짤 수 있게 생각해야겠다.


