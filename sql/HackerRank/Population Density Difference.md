## Population Density Difference
### Problem

![image](https://user-images.githubusercontent.com/84497369/182010610-3c933bfc-e926-4a35-b842-7c09b8e3ad73.png)


Query the difference between the maximum and minimum populations in CITY.


<br>

### Answer

````sql
SELECT MAX(population)-MIN(population)
FROM CITY
