# sql-1-afternoon-solutions


Table - person


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


Table - orders

1-Create a table called orders that records: order_id, person_id, product_name, product_price, quantity.

CREATE TABLE orders ( 
  order_id SERIAL PRIMARY KEY, 
  person_id INTEGER, 
  product_name VARCHAR(200), 
  product_price NUMERIC, 
  quantity INTEGER );
  
  2-Add 5 orders to the orders table.
Make orders for at least two different people.
person_id should be different for different people.

INSERT INTO orders ( person_id, product_name, product_price, quantity ) 
VALUES ( 0, 'Hat', 15.50, 3 );

INSERT INTO orders ( person_id, product_name, product_price, quantity ) 
VALUES ( 1, 'Shoes', 17.00, 1);

INSERT INTO orders ( person_id, product_name, product_price, quantity ) 
VALUES ( 2, 'Belt', 2.00, 3);

INSERT INTO orders ( person_id, product_name, product_price, quantity ) 
VALUES ( 3, 'Gloves', 5.00, 2);

INSERT INTO orders ( person_id, product_name, product_price, quantity ) 
VALUES ( 4, 'Socks', 18.00, 2);

3-Select all the records from the orders table.

SELECT * FROM orders;

4-Calculate the total number of products ordered.

SELECT SUM(quantity) FROM orders;

5-Calculate the total order price.

SELECT SUM(product_price * quantity) FROM orders;

6-Calculate the total order price by a single person_id.

SELECT SUM(product_price * quantity) FROM orders WHERE person_id = 2;



Table - artist

1-Add 3 new artists to the artist table. ( It's already created )

INSERT INTO artist ( name ) 
VALUES ( 'Degas' );
INSERT INTO artist ( name ) 
VALUES ( 'Van Gogh' );
INSERT INTO artist ( name ) 
VALUES ( 'Kadinsky' );


2-Select 10 artists in reverse alphabetical order.

SELECT * FROM artist 
ORDER BY name DESC LIMIT 10;

3-Select 5 artists in alphabetical order.

SELECT * FROM artist 
ORDER BY name ASC LIMIT 5;

4-Select all artists that start with the word 'Black'.

SELECT * FROM artist 
WHERE name LIKE 'Black%';

5-Select all artists that contain the word 'Black'.

SELECT * FROM artist 
WHERE name LIKE '%Black%';



Table - employee

1-List all employee first and last names only that live in Calgary.

SELECT first_name, last_name 
FROM employee WHERE city = 'Calgary';


2-Find the birthdate for the youngest employee.

SELECT MAX(birth_date) from employee;


3-Find the birthdate for the oldest employee.

SELECT MIN(birth_date) from employee;


4-Find everyone that reports to Nancy Edwards (Use the ReportsTo column).
You will need to query the employee table to find the Id for Nancy Edwards


SELECT * FROM employee 
WHERE reports_to = 2;

5-Count how many people live in Lethbridge.

SELECT COUNT(*) FROM employee 
WHERE city = 'Lethbridge';



Table - invoice

1-Count how many orders were made from the USA.

SELECT COUNT(*) FROM invoice
WHERE billing_country = 'USA';

2-Find the largest order total amount.

SELECT MAX(total) FROM invoice;

3-Find the smallest order total amount.

SELECT MIN(total) FROM invoice;

4-Find all orders bigger than $5.

SELECT * FROM invoice 
WHERE total > 5;

5-Count how many orders were smaller than $5.

SELECT COUNT(*) FROM invoice 
WHERE total < 5;

6-Count how many orders were in CA, TX, or AZ (use IN).


SELECT COUNT(*) FROM invoice 
WHERE billing_state in ('CA', 'TX', 'AZ');

7-Get the average total of the orders.

SELECT AVG(total) FROM invoice;

8-Get the total sum of the orders.

SELECT SUM(total) FROM invoice;















  
  
  
  





























