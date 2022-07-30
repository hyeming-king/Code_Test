## Japan Population

### Problem
Query the sum of the populations for all Japanese cities in CITY. 

The COUNTRYCODE for Japan is JPN.


![image](https://user-images.githubusercontent.com/84497369/181878581-05247cbe-bfa8-4bab-a368-f7d3a0e9da1c.png)

### Answer
````sql
SELECT SUM(population)
FROM city
WHERE countrycode = 'JPN'
````

