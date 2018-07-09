# SQL Homework

The local cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'

```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:

```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1.  Return ALL the data in the 'movies' table.

SELECT * FROM movies;

2.  Return ONLY the name column from the 'people' table

SELECT people.name FROM people;

3.  Oops! Someone at CodeClan spelled Vicky's name wrong! Change it to reflect the proper spelling ('Vicky Jackson-Five' should be 'Vicky Jackson').

UPDATE people SET name = 'Vicky Jackson' WHERE name = 'Vicky Jackson-Five';
SELECT people.name FROM people; -- check to see that Vicky has been updated

4.  Return ONLY your name from the 'people' table.

SELECT people.name
	FROM people
	WHERE people.name = 'Mark Ditzel';

5.  The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

 DELETE
 	FROM movies 
 	WHERE title = 'Batman Begins';
 
 SELECT movies.title -- check to see that Batman is missing
 	FROM movies;


6.  Create a new entry in the 'people' table with the name of one of the instructors.

INSERT INTO people (name) VALUES ('Bazza Bazlington');

SELECT people.name FROM people;


7.  Donald Trump has decided to hijack our movie evening, Remove him from the table of people.

DELETE FROM people WHERE name = 'Donald Trump';

SELECT people.name FROM people;


8.  The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies (title, year, show_time) VALUES ('Avengers: Infinity War', 2018, '00:00');

SELECT movies FROM movies;


9.  The cinema would also like to make the Guardians movies a back to back feature. Find out the show time of "Guardians of the Galaxy" and set the show time of "Guardians of the Galaxy 2" to start two hours later.

SELECT movies.show_time
FROM movies
WHERE movies.title = 'Guardians of the Galaxy';
 
UPDATE movies SET show_time = '15:05' WHERE title = 'Guardians of the Galaxy 2';
 
SELECT movies FROM movies; 	

## Extension

1.  Research how to delete multiple entries from your table in a single command.
