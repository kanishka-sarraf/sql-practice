### Vowel Problems: (Hackerrank)

Input Format:

The **STATION** table is described as follows:

![image](https://github.com/user-attachments/assets/bca07974-4844-4420-b61c-3431cff2b7ce)

where LAT_N is the northern latitude and LONG_W is the western longitude.

1. Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.
   
   ```sql
   select distinct city from station
   where lower(left(city,1)) in ('a','e','i','o','u');
   ```

2. Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

   ```sql
   select distinct city from station
   where lower(right(city,1)) in ('a','e','i','o','u');
   ```
   
3. Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

   ```sql
   select distinct city from station
   where lower(left(city,1)) in ('a','e','i','o','u')
           and lower(right(city,1)) in ('a','e','i','o','u');
   ```

4. Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

   ```sql
   select distinct city from station
   where lower(left(city,1)) not in ('a','e','i','o','u');
   ```

5. Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

   ```sql
   select distinct city from station
   where lower(right(city,1)) not in ('a','e','i','o','u');
   ```
   
6. Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

   ```sql
   select distinct city from station
   where lower(left(city,1)) not in ('a','e','i','o','u')
             or lower(right(city,1)) not in ('a','e','i','o','u');
   ```
   
7. Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

   ```sql
   select distinct city from station
   where lower(left(city,1)) not in ('a','e','i','o','u')
             and lower(right(city,1)) not in ('a','e','i','o','u');
   ```
   
