[See assignment in Alexa.](https://alexa.bitmaker.co/cohorts/72/assignments/2244/latest)

** your task is to compose SQL queries for the following questions:

Find all the robots from Star Wars.

intro_to_sql=# SELECT * FROM robots WHERE source = 'Star Wars';
 name |  source   | personality | id
------+-----------+-------------+----
 C3PO | Star Wars | anxious     |  4
 R2D2 | Star Wars | loyal       |  8
(2 rows)

Find the robot with an "anxious" personality.

intro_to_sql=# SELECT * FROM robots WHERE personality = 'anxious';
 name |  source   | personality | id
------+-----------+-------------+----
 C3PO | Star Wars | anxious     |  4
(1 row)

Find all recipes that are nut free.

intro_to_sql=# SELECT * FROM recipes WHERE nut_free = true;


Count the number of recipes that are gluten free but not vegetarian.

intro_to_sql=# SELECT * FROM recipes COUNT WHERE gluten_free  = true and vegetarian = false;
(2 rows)


Find the animal with the most legs.

intro_to_sql=# SELECT * FROM animals ORDER BY number_of_legs;
       name       | number_of_legs | flying | swimming | egg_laying | id
------------------+----------------+--------+----------+------------+----
 whale            |              0 | f      | t        | f          | 10
 hammerhead shark |              0 | f      | t        | f          |  2
 bat              |              2 | t      | f        | f          |  6
 duck             |              2 | t      | t        | t          |  4
 owl              |              2 | t      | f        | t          |  7
 chicken          |              2 | f      | f        | t          |  9
 cow              |              4 | f      | f        | f          |  8
 sheep            |              4 | f      | f        | f          |  5
 cat              |              4 | f      | f        | f          |  1
 octopus          |              8 | f      | t        | t          |  3
(10 rows)

intro_to_sql=# SELECT MAX(number_of_legs) FROM animals;
 max
-----
   8
(1 row)

Find the board game that takes the least amount of time to play.

intro_to_sql=# SELECT MIN(mins_to_play) FROM board_games;
 min
-----
  15
(1 row)

Find the recipe that takes the most time to prepare.

intro_to_sql=# SELECT MAX(minutes_required) FROM recipes;
 max
-----
 390
(1 row)

Find all the robots whose name starts with the letter M.

intro_to_sql=# SELECT * FROM robots WHERE name LIKE 'M%'
intro_to_sql-# ;
      name      |                source                |  personality  | id
----------------+--------------------------------------+---------------+----
 Marvin         | The Hitchhiker's Guide to the Galaxy | pessimistic   |  3
 Mr. Butlertron | Clone High                           | compassionate |  5
(2 rows)


Count the number of board games that can be played by 8 people.

intro_to_sql=# SELECT * FROM board_games COUNT WHERE max_players = 8;
     name      | max_players | min_players | category | mins_to_play | id
---------------+-------------+-------------+----------+--------------+----
 Arkham Horror |           8 |           1 | strategy |          240 |  1
(1 row)

Find all animals that are swimming and egg-laying.

intro_to_sql=# SELECT * FROM animals WHERE swimming = true and egg_laying = true;
  name   | number_of_legs | flying | swimming | egg_laying | id
---------+----------------+--------+----------+------------+----
 octopus |              8 | f      | t        | t          |  3
 duck    |              2 | t      | t        | t          |  4
(2 rows)

Find all animals that are swimming and egg-laying but not flying.

intro_to_sql=# SELECT * FROM animals WHERE swimming = true and egg_laying = true and flying = false;
  name   | number_of_legs | flying | swimming | egg_laying | id
---------+----------------+--------+----------+------------+----
 octopus |              8 | f      | t        | t          |  3
(1 row)

Find the board game that supports the largest number of people.

intro_to_sql=# SELECT MAX(max_players) FROM board_games
intro_to_sql-# ;
 max
-----
  30
(1 row)
