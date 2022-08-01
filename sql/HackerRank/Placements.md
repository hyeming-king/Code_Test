## Placements

### Problem

학생의 친한 친구가 학생보다 월급을 많이 받는 경우에 이름을 출력하여라 (학생 이름)

<img width="273" alt="image" src="https://user-images.githubusercontent.com/84497369/182169572-17c608ee-e0ec-464b-9f32-2b59cf12cd9b.png">



### Answer

<img width="423" alt="image" src="https://user-images.githubusercontent.com/84497369/182169792-3598201d-8eb9-45ea-86de-3a779ab139b1.png">

설명을 위해 예시로 든 표를 먼저 만들어 보기로 생각하면서 문제를 풀었다.

````sql
SELECT s.name
--        , s.id, p1.salary, f.friend_id, p2.salary
FROM Students s
  INNER JOIN friends f
  ON s.id = f.id
  INNER JOIN packages p1
  ON s.id = p1.id
  INNER JOIN packages p2
  ON f.friend_id = p2.id
WHERE p2.salary > p1.salary
ORDER BY p2.salary
````

