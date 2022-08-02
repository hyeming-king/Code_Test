## Binary Tree Nodes
### Problem


- Root: If node is root node.
- Leaf: If node is leaf node.
- Inner: If node is neither root nor leaf node


Table : BST

<img width="276" alt="image" src="https://user-images.githubusercontent.com/84497369/182366836-be785cd6-1798-4163-9aa2-d0a60dd91f15.png">

N : 노드 / P : 부모 노드


<예시>


<img width="262" alt="image" src="https://user-images.githubusercontent.com/84497369/182366708-ce860495-9d0b-48b8-9b86-d68689fca5a1.png">
<img width="478" alt="image" src="https://user-images.githubusercontent.com/84497369/182366730-a90c4938-c54f-4441-aed9-4eedaed1fb5f.png">



node가 주어졌을 때, 루트, 리프, 이너 노드를 출력하는 쿼리를 작성하시오.



### Answer

해당 문제를 풀때 결과에 부합하는 조건 3가지를 생각하였습니다.

1. <BST> 테이블에서 P의 값이 NULL이면 'ROOT'
2. P의 값에 해당하지 않는 것이 'Leaf' (제일 아래) 노드
3. 나머지는 'Inner' 노드이다.
  
  
  
```sql
 SELECT N
     , CASE 
            WHEN P IS NULL THEN 'Root'
            WHEN N IN (SELECT N
                        FROM BST
                        WHERE N NOT IN (SELECT DISTINCT P
                                        FROM BST
                                        WHERE P IS NOT NULL)) THEN 'Leaf'
            ELSE 'Inner'
      END AS node
FROM BST
ORDER BY N 
  
```
