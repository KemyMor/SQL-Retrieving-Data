# SQL-Retrieving-Data
Retrieving Data using The Select Statement, Where, CASE And Operator Statement.

## CASE 1 
---- Find the job title in the "Software developement" department that have a work life balance rating greater than 4 and a salary and benefits rating greater than 4.5.--
+ SELECT Title From Employee_Review
+ WHERE Department = 'Software Development Department'
+ AND work_life_balance > 4
+ AND salary_and_benefits > 4.5;

# CASE 2
---- using case statement, create a new column that specifies everything greater than 4 for the whole qualities as 'excellent', having atleast two qualities greater than 3 as 'Good' and everyother thing as 'poor'----

+ SELECT *, CASE WHEN Overall_rating > 4 AND work_life_balance > 4 AND skill_development > 4 
					AND salary_and_benefits > 4 AND job_security > 4 AND career_growth > 4 
					AND work_satisfaction > 4 THEN 'EXCELLENT'
	           WHEN career_growth > 3 AND work_life_balance > 3 OR job_security > 3 THEN 'GOOD'
	           WHEN Overall_rating <3 AND work_life_balance < 3 AND skill_development < 3 
					AND salary_and_benefits < 3 AND job_security < 3 AND career_growth < 3 
					AND work_satisfaction < 3 THEN 'POOR'
          END AS APPRAISALS
+ FROM Employee_Review;

