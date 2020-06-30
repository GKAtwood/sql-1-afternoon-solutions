# sql-1-afternoon-solutions

1-Create a table called person that records a person's id, name, age, height ( in cm ), city, favorite_color.
id should be an auto-incrementing id/primary key - Use type: SERIAL

create table person(
person_id serial,
person_name varchar(25),
person_age integer,
person_height numeric,
person_city varchar(45),
favorite_color varchar(15)
);

2-Add 5 different people into the person database.
Remember to not include the person_id because it should auto-increment.

insert into person(
person_name, 
person_age,
person_height, 
person_city, 
favorite_color 


)values(
'Lola',
 8, 
68,
'Portland',
'Pink'  
);

insert into person(
person_name, 
person_age,
person_height, 
person_city, 
favorite_color 


)values(
'Ricky',
 5, 
58,
'Gotham',
'Black'  
);

insert into person(
person_name, 
person_age,
person_height, 
person_city, 
favorite_color 


)values(
'Scott',
 28, 
178,
'Los Angeles',
'Purple'  
);

insert into person(
person_name, 
person_age,
person_height, 
person_city, 
favorite_color 


)values(
'Max',
 25, 
180,
'Milan',
'Blue'  
);

insert into person(
person_name, 
person_age,
person_height, 
person_city, 
favorite_color 


)values(
'Annie',
 27, 
150,
'Busan',
'Turquoise'  
);


3-List all the people in the person table by height from tallest to shortest.

select * from person
order by person_height DESC;




4-List all the people in the person table by height from shortest to tallest.

select * from person
order by person_height ASC;

5-List all the people in the person table by age from oldest to youngest.

select * from person
order by person_age DESC;

6-List all the people in the person table older than age 20.

select person_name, person_age from person
where person_age > 20;

7-List all the people in the person table that are exactly 18.

select person_name, person_age from person
where person_age = 18;

8-List all the people in the person table that are less than 20 and older than 30.

select person_name, person_age from person
where person_age < 20 OR person_age > 30;

9-List all the people in the person table that are not 27 (Use not equals).

select person_name, person_age from person
where person_age != 27;

10-List all the people in the person table where their favorite color is not red.

select person_name, favorite_color from person
where favorite_color != 'red';

11-List all the people in the person table where their favorite color is not red and is not blue.

select person_name, favorite_color from person
where favorite_color != 'Blue' AND favorite_color != 'Red';

12-List all the people in the person table where their favorite color is orange or green.

select person_name, favorite_color from person
where favorite_color = 'Green' OR favorite_color = 'Orange';

13-List all the people in the person table where their favorite color is orange, green or blue (use IN).

SELECT  person_name, favorite_color
FROM person
WHERE favorite_color IN ('Orange', 'Green', 'Blue');

14-List all the people in the person table where their favorite color is yellow or purple (use IN).

SELECT  person_name, favorite_color
FROM person
WHERE favorite_color IN ('Yellow', 'Purple');



























