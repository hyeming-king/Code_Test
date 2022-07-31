## Weather Observation Station 11

### Problem
![image](https://user-images.githubusercontent.com/84497369/182010778-c175bbc8-d259-4e28-8363-d5202a061fef.png)

Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. <br>
Your result cannot contain duplicates.


### Answer

````
SELECT DISTINCT city
FROM station
WHERE city REGEXP '^[^AEIOUaeiou]|[^AEIOUaeiou]$'
````

주의) 모음으로 시작하지 않거나 ! 모음으로 끝나지 않는!
