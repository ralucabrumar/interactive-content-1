[slide hideTitle]

# Wildcards

**Wildcard** symbols in MySQL substitute one or more **characters** in a string.

| Symbol | Description |
| --- | --- |
| % | Represents zero or more characters |
| _ | Represents a single character |
| ^ | Represents any character that is not in brackets |
| [] | Represents any single character within the brackets |
| - | Represents a range of characters |

We use them with the **LIKE** operator in a **WHERE** clause. 

It is pretty similar to how **regular expressions** work.

Here are a few **examples**.

- Finding any values that **start with "a"** (Customer name in our case):

``` java
WHERE CustomerName LIKE 'a%'; 
```

- Here we are looking for values that have **"r"** in their **second position**:

``` java
WHERE CustomerName LIKE '_r%'; 
```

- The following code will find values that **start with "a"**, and **end with "o"**:
  
``` java
WHERE ContactName LIKE 'a%o'; 
```

The \[charlist\] wildcards specify **which characters** to look for.

Similarly, we can use the \[!charlist\] wildcard to specify **excluding** characters.

## Using Regular Expressions

We can also use the `REGEXP` function to match it to any pattern.

**For example**:

``` java
SELECT * FROM `customers` 
WHERE `city` REGEXP '[a-c]%'; 
```

In the above case, we will look for a **city**, named **either "a" , "b" or "c"**.

[/slide]


[slide hideTitle]
# Problem and Solution: Harry Potter Books
[code-task title="Harry Potter Books" taskId="java-db-and-mysql-built-in-functions-and-data-aggregation-harry-potter-books" executionType="tests-execution" executionStrategy="mysql-prepare-db-and-run-queries" requiresInput]
[code-editor language=sql]
```
-- Write your query here
```
[/code-editor]
[task-description]

**Use the booklibrary database.**

Write an SQL query to retrieve the titles of all Harry Potter books. 

**Order the information by id.** 

## Example

| title |
| --- |
| Harry Potter and the Philosopher's Stone |
| Harry Potter and the Chamber of Secrets |
| Harry Potter and the Prisoner of Azkaban |
| ... |


[/task-description]
[code-io /]
[tests]
[test open]
[input]
CREATE TABLE authors (
	id INT PRIMARY KEY AUTO_INCREMENT,
	first_name VARCHAR(30) NOT NULL,
	middle_name VARCHAR(30),
	last_name VARCHAR(30) NOT NULL,
	born DATETIME NOT NULL,
	died DATETIME
);

INSERT INTO authors(id,first_name, middle_name, last_name, born, died) VALUES
	(1,'Agatha', 'Mary Clarissa','Christie', '1890-09-15', '1976-01-12'),
	(2,'William', NULL,'Shakespeare', '1564-04-26', '1616-04-23'),
	(3,'Danielle', 'Fernandes Dominique', 'Schuelein-Steel', '1947-07-14', NULL),
	(4,'Joanne', NULL,'Rowling' , '1965-07-31', NULL),
	(5,'Lev', 'Nikolayevich', 'Tolstoy', '1828-09-09', '1910-11-20'),
	(6,'Paulo', 'Coelho de', 'Souza', '1947-08-24', NULL),
	(7,'Stephen', 'Edwin', 'King', '1947-09-21', NULL),
	(8,'John', 'Ronald Reuel', 'Tolkien', '1892-01-03', '1973-09-02'),
	(9,'Erika', NULL, 'Mitchell', '1963-03-07', NULL);
	
CREATE TABLE books (
	id INT PRIMARY KEY AUTO_INCREMENT,
	title VARCHAR(100) NOT NULL,
	author_id INT NOT NULL,
	year_of_release DATETIME,
	cost DOUBLE NOT NULL,
	CONSTRAINT fk_author_id FOREIGN KEY (author_id) REFERENCES authors(id)
);

INSERT INTO books(author_id,title, year_of_release,cost) VALUES
	(1,'Unfinished Portrait', '1930-01-02', 15.99),
	(1,'The Mysterious Affair at Styles', '1920-01-02',17.99),
	(1,'The Big Four', '1927-01-02',14.99),
	(1,'The Murder at the Vicarage', '1930-01-02',13.99),
	(1,'The Mystery of the Blue Train', '1928-01-02',12.99),
	(2,'Julius Caesar', '1599-01-02',11.99),
	(2,'Timon of Athens', '1607-01-02',13.99),
	(2,'As You Like It', '1600-01-02',18.99),
	(2,'A Midsummer Night''s Dream', '1595-01-02',15.99),
	(3,'Going Home', '1973-01-02',15.99),
	(3,'The Ring', '1980-01-02',14.99),
	(3,'Secrets', '1985-01-02',15.99),
	(3,'Message From Nam', '1990-01-02',13.99),
	(4,'Career of Evil', '2015-01-02',15.99),
	(4, 'Harry Potter and the Philosopher''s Stone','1997-01-02',19.99),
	(4,'Harry Potter and the Chamber of Secrets','1998-01-02',19.99),
	(4,'Harry Potter and the Prisoner of Azkaban','1999-01-02',19.99),
	(4,'Harry Potter and the Goblet of Fire','2000-01-02',19.99),
	(4,'Harry Potter and the Order of the Phoenix','2003-01-02',19.99),
	(4,'Harry Potter and the Half-Blood Prince','2005-01-02',19.99),
	(4,'Harry Potter and the Deathly Hallows','2007-01-02',19.99),
	(4,'Harry Potter and the Deathly Hallows','2007-01-02',15.99),
	(5,'Anna Karenina','1877-01-02',15.99),
	(5,'War And Peace','1869-01-02',30),
	(5,'Boyhood','1854-01-02',15.99),
	(6,'By the River Piedra I Sat Down and Wept','1994-01-02',15.99),
	(6,'The Alchemist','1988-01-02',15.99),
	(6,'The Fifth Mountain','1996-01-02',15.99),
	(6,'The Zahir','2005-01-02',15.99),
	(7,'Rage','1977-01-02',13.99),
	(7,'The Dead Zone','1979-01-02',13.99),
	(7,'It','1986-01-02',13.99),
	(7,'It','1986-01-02',13.99),	
	(8,'The Hobbit','1937-01-02',20.99),	
	(8,'The Adventures of Tom Bombadil','1962-01-02',13.99),	
	(9,'Fifty Shades of Grey','2011-01-02',13.99),	
	(9,'Fifty Shades Darker','2012-01-02',13.99),	
	(9,'Fifty Shades Freed','2012-01-02',13.99);
[/input]
[output]
Harry Potter and the Philosopher's Stone
Harry Potter and the Chamber of Secrets
Harry Potter and the Prisoner of Azkaban
Harry Potter and the Goblet of Fire
Harry Potter and the Order of the Phoenix
Harry Potter and the Half-Blood Prince
Harry Potter and the Deathly Hallows
Harry Potter and the Deathly Hallows
[/output]
[/test]
[test]
[input]
CREATE TABLE authors (
	id INT PRIMARY KEY AUTO_INCREMENT,
	first_name VARCHAR(30) NOT NULL,
	middle_name VARCHAR(30),
	last_name VARCHAR(30) NOT NULL,
	born DATETIME NOT NULL,
	died DATETIME
);

INSERT INTO authors(id,first_name, middle_name, last_name, born, died) VALUES
	(1,'Agatha', 'Mary Clarissa','Christie', '1890-09-15', '1976-01-12'),
	(2,'William', NULL,'Shakespeare', '1564-04-26', '1616-04-23'),
	(3,'Danielle', 'Fernandes Dominique', 'Schuelein-Steel', '1947-07-14', NULL),
	(4,'Joanne', NULL,'Rowling' , '1965-07-31', NULL),
	(5,'Lev', 'Nikolayevich', 'Tolstoy', '1828-09-09', '1910-11-20'),
	(6,'Paulo', 'Coelho de', 'Souza', '1947-08-24', NULL),
	(7,'Stephen', 'Edwin', 'King', '1947-09-21', NULL),
	(8,'John', 'Ronald Reuel', 'Tolkien', '1892-01-03', '1973-09-02'),
	(9,'Erika', NULL, 'Mitchell', '1963-03-07', NULL);
	
CREATE TABLE books (
	id INT PRIMARY KEY AUTO_INCREMENT,
	title VARCHAR(100) NOT NULL,
	author_id INT NOT NULL,
	year_of_release DATETIME,
	cost DOUBLE NOT NULL,
	CONSTRAINT fk_author_id FOREIGN KEY (author_id) REFERENCES authors(id)
);

INSERT INTO books(author_id,title, year_of_release,cost) VALUES
	(1,'Unfinished Portrait', '1930-01-02', 15.99),
	(1,'The Mysterious Affair at Styles', '1920-01-02',17.99),
	(1,'The Big Four', '1927-01-02',14.99),
	(1,'The Murder at the Vicarage', '1930-01-02',13.99),
	(1,'The Mystery of the Blue Train', '1928-01-02',12.99),
	(2,'Julius Caesar', '1599-01-02',11.99),
	(2,'Timon of Athens', '1607-01-02',13.99),
	(2,'As You Like It', '1600-01-02',18.99),
	(2,'A Midsummer Night''s Dream', '1595-01-02',15.99),
	(3,'Going Home', '1973-01-02',15.99),
	(3,'The Ring', '1980-01-02',14.99),
	(3,'Secrets', '1985-01-02',15.99),
	(3,'Message From Nam', '1990-01-02',13.99),
	(4,'Career of Evil', '2015-01-02',15.99),
	(4, 'Harry Potter and the Philosopher''s Stone','1997-01-02',19.99),
	(4,'Harry Potter and the Chamber of Secrets','1998-01-02',19.99),
	(4,'Harry Potter and the Prisoner of Azkaban','1999-01-02',19.99),
	(4,'Harry Potter and the Goblet of Fire','2000-01-02',19.99),
	(4,'Harry Potter and the Order of the Phoenix','2003-01-02',19.99),
	(4,'Harry Potter and the Half-Blood Prince','2005-01-02',19.99),
	(4,'Harry Potter and the Deathly Hallows','2007-01-02',19.99),
	(4,'Harry Potter and the Deathly Hallows','2007-01-02',15.99),
	(5,'Anna Karenina','1877-01-02',15.99),
	(5,'War And Peace','1869-01-02',30),
	(5,'Boyhood','1854-01-02',15.99),
	(6,'By the River Piedra I Sat Down and Wept','1994-01-02',15.99),
	(6,'The Alchemist','1988-01-02',15.99),
	(6,'The Fifth Mountain','1996-01-02',15.99),
	(6,'The Zahir','2005-01-02',15.99),
	(7,'Rage','1977-01-02',13.99),
	(7,'The Dead Zone','1979-01-02',13.99),
	(7,'It','1986-01-02',13.99),
	(7,'It','1986-01-02',13.99),	
	(8,'The Hobbit','1937-01-02',20.99),	
	(8,'The Adventures of Tom Bombadil','1962-01-02',13.99),	
	(9,'Fifty Shades of Grey','2011-01-02',13.99),	
	(9,'Fifty Shades Darker','2012-01-02',13.99),	
	(9,'Fifty Shades Freed','2012-01-02',13.99);
[/input]
[output]
Harry Potter and the Philosopher's Stone
Harry Potter and the Chamber of Secrets
Harry Potter and the Prisoner of Azkaban
Harry Potter and the Goblet of Fire
Harry Potter and the Order of the Phoenix
Harry Potter and the Half-Blood Prince
Harry Potter and the Deathly Hallows
Harry Potter and the Deathly Hallows
[/output]
[/test]
[/tests]
[/code-task]
[/slide]

