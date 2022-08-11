## Contest Leaderboard
### Problem

문제를 이해하는 게 조금 어려웠다.
다시 영어의 중요성을 깨닫는다.

<조건> 

- 해커가 푼 챌린지 문제의 총합을 구하라
- 동일한 챌린지 문제를 여러번 푼 경우에는 가장 높은 값만 인정한다.
- score 순서대로 내림차순으로 정렬
- score 점수가 같다면 이름 오름차순으로 정렬
- 총 score가 0점이 해커는 출력하지 않는다.

Table : Hackers

<img width="152" alt="image" src="https://user-images.githubusercontent.com/84497369/184071808-b61c7fe1-475c-44ef-aa96-490f1f5dce8c.png">




Table : submission

<img width="160" alt="image" src="https://user-images.githubusercontent.com/84497369/184071819-b7aa1e54-42f1-4d68-92cd-d7d51c3e50c8.png">


### Answer

해당 문제를 풀때 결과에 이러한 방식으로 접근하였습니다.

1. submission_id(문제 풀때의 세션 느낌)보다 challenge_id(문제)에 초점을 맞춰서, 해커가 푼 문제의 최고 점수로 접근하기
  => **문제별 group by로 접근**
2. score가 0이상인 경우만 고려해줌
  
  
```sql
SELECT s.hacker_id, name, SUM(total) as all_sum
FROM (SELECT hacker_id, challenge_id, MAX(score) as total
      FROM submissions
      WHERE score > 0 
      GROUP BY hacker_id, challenge_id
      ORDER BY hacker_id, challenge_id ) s
LEFT JOIN hackers h
  ON s.hacker_id = h.hacker_id
GROUP BY s.hacker_id, name
ORDER BY all_sum desc, s.hacker_id
```
