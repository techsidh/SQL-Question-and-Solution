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

####Query 3 : Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates. 
