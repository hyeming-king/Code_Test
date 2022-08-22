## Ollivander's Inventory
### Problem

헤르미온느는 론에게 지팡이를 추천해주고 싶다.

- non_evil
- high power
- high age
- minimum number of gold galleons

<br>

- id , age , coins_needed , power 를 출력하라
- power / age 내림차순 / coins_needed 적은 값

Wands

<img width="178" alt="image" src="https://user-images.githubusercontent.com/84497369/185825725-3c1c4007-d8b6-480a-973b-c0c69ef71063.png">

Wands_Property

<img width="150" alt="image" src="https://user-images.githubusercontent.com/84497369/185825691-74c13829-3a5e-489b-90d8-9ce99a8805be.png">


### Answer

접근방식
- is_evil = 0 (사악하지 않다.)
- Wands.code = Wands_Property.code 로 태이블을 조인 필요
- power, age 가 동일하면 MIN 가격(coins_needed) 만 출력해야한다.
- code와 age는 1:1관계
- 서브쿼리로 power, code 별로 가장 작은 MIN(coins_needed)를 가져오기
- id , age , coin_needed , power 출력 / power 내림차순 순으로 그다음 age 내림차순

```sql
SELECT w.id
     , wp.age
     , w.coins_needed
     , w.power
FROM Wands w
    INNER JOIN Wands_Property wp
    ON w.code = wp.code
WHERE wp.is_evil = 0
AND (w.power, w.code, w.coins_needed) IN (SELECT power, code, MIN(coins_needed)
                                           FROM Wands
                                           GROUP BY power, code)
ORDER BY w.power desc, wp.age desc
```
