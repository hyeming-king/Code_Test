## Weather Observation Station 12

### Problem

![image](https://user-images.githubusercontent.com/84497369/182011975-0d8857d7-fb64-47f2-9608-ae5309e8cec0.png)

Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. <br>
Your result cannot contain duplicates.


<br>
### Answer

```sql
-- 정규식으로
SELECT DISTINCT city
FROM station
WHERE city REGEXP '^[^a,e,i,o,u].*[^a,e,i,o,u]$'


-- LIKE 활용하여
SELECT DISTINCT city
FROM station
WHERE city NOT LIKE 'a%'
AND city NOT LIKE 'e%'
AND city NOT LIKE 'i%'
AND city NOT LIKE 'o%'
AND city NOT LIKE 'u%'
AND city NOT LIKE '%a'
AND city NOT LIKE '%e'
AND city NOT LIKE '%i'
AND city NOT LIKE '%o'
AND city NOT LIKE '%u'
```
