## New Companies

### Problem
회사가 아래의 구조처럼 생겼을 떄,

![image](https://user-images.githubusercontent.com/84497369/182027672-92698077-0352-4ffb-bd7f-b09c94b727a0.png)

[ 회사번호, 설립자, 리드 매니저 수, 시니어 매니저 수, 매니저 수, 직원 수 ] 를 구하여라


Company <br>
![image](https://user-images.githubusercontent.com/84497369/182027736-dd19be4c-7021-45f1-82e4-706a8fdef655.png)

Lead_Manager <br>
![image](https://user-images.githubusercontent.com/84497369/182027746-fb0a1e7d-ee3c-4c1f-bd31-437b78b1aee0.png)

Senior_Manager <br>
![image](https://user-images.githubusercontent.com/84497369/182027756-fd074e81-8070-4cfe-9590-72a2a195a460.png)

Manager <br>
![image](https://user-images.githubusercontent.com/84497369/182027760-013b6414-0993-4a93-bc01-aa272d123438.png)

Employee <br>
![image](https://user-images.githubusercontent.com/84497369/182027769-c339d8d9-9c17-4f9d-a607-09ff424bb58c.png)



### Answer

```sql
SELECT c.company_code
     , c.founder
     , num_lead
     , num_s_manager
     , num_manager
     , num_employee
FROM company c
INNER JOIN (SELECT COUNT(DISTINCT employee_code) AS num_employee
            , COUNT(DISTINCT manager_code) AS num_manager
            , COUNT(DISTINCT senior_manager_code) AS num_s_manager
            , COUNT(DISTINCT lead_manager_code) AS num_lead
            , company_code
            FROM employee
            GROUP BY company_code) AS em
ON c.company_code = em.company_code
ORDER BY c.company_code
```


- 테이블이 너무 많아 헷갈렸었다.
- 가능한 많은 정보를 얻을 수 있는 테이블 위주로 문제를 접근

- employee 테이블에서 회사번호에 따른 리드, 시니어 매니저, 매니저, 직원 수를 얻은 후에, company 테이블과 조인하는 형식을 사용하였다.
