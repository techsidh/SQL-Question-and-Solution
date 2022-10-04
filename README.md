####Query 1 : Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

Solution : (select CITY, length(CITY)
            from STATION 
            order by length(CITY) asc, CITY asc limit 1) 
            union 
            (select CITY, length(city)
             from STATION  
             order by length(CITY) desc, CITY asc limit 1);

####Query 2 : Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.
Solution : SELECT distinct(CITY)
           FROM STATION
           where city REGEXP '^[aeiou]'

####Query 3 : Generate the following two result sets:

Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).
Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:

There are a total of [occupation_count] [occupation]s.
Solution : 

select concat(name,'(',upper(substring(occupation,1,1)),')')
from occupations
order by name;

select concat("There are a total of",' ',count(occupation),' ',lower(occupation),'s',".")
from occupations
group by occupation
order by count(occupation) asc;


