### Practice Questions

#### 1. Types of Triangle 
https://www.hackerrank.com/challenges/what-type-of-triangle/problem

Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

- Equilateral: It's a triangle with  sides of equal length.
- Isosceles: It's a triangle with  sides of equal length.
- Scalene: It's a triangle with  sides of differing lengths.
- Not A Triangle: The given values of A, B, and C don't form a triangle.

Input Format

The **TRIANGLES** table is described as follows:

![image](https://github.com/user-attachments/assets/a95d0107-79cc-474e-a51a-74f2e2ffb11e)

Each row in the table denotes the lengths of each of a triangle's three sides.

```sql
select -- a,b,c,
case when (a+b)<=c or (b+c)<=a or (a+c)<=b then 'Not A Triangle'
     when (a = b) and (b = c) then 'Equilateral'
     when (a = b) or (b = c) or (c = a) then 'Isosceles'
     -- when (a = b and b != c) or (a = c and b != c) or (c = b and a != c) then 'Isosceles'
     else 'Scalene'
end as type
from triangles;
```

#### 2. The Report
https://www.hackerrank.com/challenges/the-report/problem

You are given two tables: Students and Grades. Students contains three columns ID, Name and Marks.

![image](https://github.com/user-attachments/assets/6ca653c5-41dc-4b90-a74c-e5bfc9e462d3)

Grades contains the following data:

![image](https://github.com/user-attachments/assets/2fb89e2a-4d44-44e5-9299-33d1c306bebb)

Ketty gives Eve a task to generate a report containing three columns: Name, Grade and Mark. Ketty doesn't want the NAMES of those students who received a grade lower than 8. The report must be in descending order by grade -- i.e. higher grades are entered first. If there is more than one student with the same grade (8-10) assigned to them, order those particular students by their name alphabetically. Finally, if the grade is lower than 8, use "NULL" as their name and list them by their grades in descending order. If there is more than one student with the same grade (1-7) assigned to them, order those particular students by their marks in ascending order.

Write a query to help Eve.

```sql
select
case when grade < 8 then null else name end as name,
grade, marks
from (
select s.name,g.grade,s.marks from students s
inner join grades g
          on s.marks >= min_mark and s.marks <= max_mark
) t order by grade desc, name asc, marks asc;
```


