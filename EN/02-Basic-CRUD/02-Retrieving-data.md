[slide hideTitle]

# Retrieving Data

Let us have a look over one of the most common operations when we are talking about databases.

Retrieving data is the action of pulling data from our database based on specific criteria.

**Retrieving all available information from a table:**

``` java
SELECT * FROM students;
```


**Retrieving only the columns you need::**

``` java
SELECT full_name, course, grade FROM students; 
```


When retrieving data in this way, the resulting dataset is called a projection. 

We take only data that we need, which optimizes our query uses less resources.

**Retrieving a subset of rows:**

``` java
SELECT full_name, grade                  
FROM students                              
WHERE courseName = "Java Advanced";
```

This operation will not boost the performance, as the database has to iterate through all the records to find the one that meets the requirements, but it will find you only the records that you need based on the condition after the WHERE keyword.


**Joining tables:**

``` java
SELECT course_name, course_schedule, teacher_full_name  
FROM Orders                                                  
INNER JOIN Customers ON Courses.teacherId=Teachers.id;          
```

[image assetsSrc="Retrieving-data(3).png" /]

We will learn how to do this in the next lesson, for now just note that there is a way to display **related** data from two separate tables.

[/slide]

[slide hideTitle]

# Problem with Solution: Select Employee Information

TODO: Add task

[/slide]

[slide hideTitle]

# Problem with SOlution: Select Employees with Filter

TODO: Add task

[/slide]

[slide hideTitle]

# Other comparison conditions

Here are some other useful conditions you can specify after the WHERE keyword.


``` java
SELECT first_name                                        
FROM students                                               
WHERE NOT (course_name = 'JS Basics' AND 'Java Basics')       
```

This will select all records where course_name is not equal to the specified values.

There is an another syntax that you can use instead - `WHERE course_name NOT IN('JS Basics', 'Java Basics')`.


The **NOT** keyword is something you may have already used in your Java projects as the **!** logical NOT operator.

Following the same logic, the keyword **AND** is equal to the **&& operator** in Java.


Let's have a look over the 'OR' keyword.

```java
SELECT concat_ws(' ', first_name, last_name) AS full_name      
FROM students                                                    
WHERE course_name = 'JS Basics' AND 'Java Basics'                 
```

`concat_ws` is a function that concatenates two or more columns using a specified separator.

Its syntax is this `CONCAT_WS (separator, argument1, argument2, ... )`

Additionally we are displaying the concatenated information in a column called **full_name**.

This is purely for displaying the information and it will have no effect on the data within the students  table.


The equivalent of **OR** in Java would be **|| operator**.


Let us have a look over a few operators that are native only to SQL.



```java
SELECT concat_ws(' ', first_name, last_name) AS full_name`     
FROM `students`                                                     
WHERE `age` BETWEEN 14 AND 18                                       
```

The **BETWEEN** operator is used in combination with the **AND** operator to set the boundaries of the filtration we want.

The operator is inclusive, so it's taken into notice both boundaries. 

The values can be numbers, text, or even dates.


```java                                                                   
SELECT *                                                               
FROM students                                                          
WHERE course IN ('Java Basics', 'Java Fundamentals', 'Java Advanced')  
```

We want to use **IN/NOT IN** operators when we know the exact value we want, following the same logic we can understand what the **NOT IN** operator does.
[/slide]

[slide hideTitle]

# Problem with Solution: Select Employees by Multiple Filters

TODO: add task
[/slide]

[slide hideTitle]

# Comparison with NULL

One tricky part of SQL is the **NULL** value, it may sometimes surprise you until you finally get the hang of it.

First, we have to understand that **NULL** does not mean **No value** it conceptually means **unavailable, unassigned, unknown, or inapplicable** and it's treated somewhat differently from other values.

Null is not the same as zero or space. Zero is a number, and space is a character. 

## Arithmetic comparison and NULL

When we are talking about **NULL**, we should always be careful with its behavior when we compare it with **><=**, as it does not give us the results we expect.

```java
SELECT 1 = NULL, 1 <> NULL, 1 < NULL, 1 > NULL;
+----------+-----------+----------+----------+
| 1 = NULL | 1 <> NULL | 1 < NULL | 1 > NULL |
+----------+-----------+----------+----------+
|     NULL |      NULL |     NULL |     NULL |
+----------+-----------+----------+----------+
```

Any arithmetic comparison with **NULL** always returns the same result **NULL**. 


## IS NULL / IS NOT NULL

The proper way of checking if the given value of a record is **NULL** is by using the **IS NULL / IS NOT NULL** operators, they work simply by checking if the given statement is true or false.

```java
SELECT 'A' IS NULL, 'A' IS NOT NULL
+-----------+---------------+
|'A' IS NULL| 'A' IS NOT NULL|
+-----------+---------------+
|   false   |          true |
+-----------+---------------+
```

Arithmetic divisions with **NULL** should also be taken into account, if you want to make any arithmetic operation with **NULL** is always equal to **NULL**, for instance: 

```java
SELECT 3 - NULL // = NULL 
```

[/slide]

[slide hideTitle]

# Sorting Results

When we finish with selecting and filtering the info, we can sort it in any way we want.

We use the **ORDER BY** clause, which orders the information by a chosen column or columns, the **ORDER BY** statement is always placed last in the query.

You can use **ASC** (ascending) and **DESC** (descending) the keywords to reverse the order of the results.

By default the **ORDER BY** clause uses **ASC** strategy.

```java
SELECT *                              //Here we choose all the information
FROM students                      //for the table students
WHERE age BETWEEN 14 AND 50         //filtered by where they meet the condition
ORDER BY age DESC                   // Ordered by their age descending.
```

We select all the information from the **students** table, retrieve everyone who is between 14 and 50 years old, and **order them by age** in **descending order**.

You can chain **ORDER BY** clauses by declaring the second column by which you want to order them, separating them with a **,** in between just as in the example

```java
SELECT *                
FROM `student`
WHERE `age` BETWEEN 14 AND 50    
ORDER BY `age` DESC, `first_name` 
```

In the example above, the results would be ordered in descending order by **age** and then by the **first_name** in ascending order because **ASC** is the default sorting.

[/slide]

[slide hideTitle]

# Using Views

Views are virtual tables that do not store information by themselves.

They are used when you have written a complex query that takes records from a table or many tables and you would like to save them for future use or when you want to restrict access to data for certain users.

In other words **Views** are nothing but **saved SQL queries**.

For example:

```java
CREATE VIEW StudentsView AS                             
SELECT full_name, course, study_hours
FROM students
```

This is how views can also be used to restrict access to data.

Imagine you are working in an organization where only you are supposed to know the salaries of the other employees, but you want to grant access to someone else who needs to only be able to see contact details.

You could create a view for them and include only the relevant columns.

After that grant them access only to that view and not to the employees table.

This way of access management is quite common in organizations where certain people should have limited access but still be able to access parts of the database.

[/slide]

[slide hideTitle]
# Problem with Solution: Top Paid Employee

TODO: Add task

[/slide]