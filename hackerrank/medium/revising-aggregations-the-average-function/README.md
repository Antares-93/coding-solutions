# New Companies

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

Query the average population of all cities in **CITY** where *District* is **California**. 




**Input Format**

The **CITY** table is described as follows:
<img src="https://s3.amazonaws.com/hr-challenge-images/8137/1449729804-f21d187d0f-CITY.jpg" title="CITY.jpg" />

**Output Format**

## Solution

**Language:** SQL  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-09-19T08:05:32.189Z  

```sql
/*
Enter your query here.
*/SELECT 
    c.company_code, 
    c.founder, 
    COUNT(DISTINCT lm.lead_manager_code), 
    COUNT(DISTINCT sm.senior_manager_code), 
    COUNT(DISTINCT m.manager_code), 
    COUNT(DISTINCT e.employee_code)
FROM Company c
JOIN Lead_Manager lm ON c.company_code = lm.company_code
JOIN Senior_Manager sm ON lm.lead_manager_code = sm.lead_manager_code
JOIN Manager m ON sm.senior_manager_code = m.senior_manager_code
JOIN Employee e ON m.manager_code = e.manager_code
GROUP BY c.company_code, c.founder
ORDER BY c.company_code ASC;

```

---

[View on HackerRank](https://www.hackerrank.com/challenges/revising-aggregations-the-average-function/problem)