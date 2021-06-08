[slide hideTitle]

# String Functions

We use **string** functions to manipulate our character string effectively.

Example of **string functions**:

## The SUBSTRING() Function

The `SUBSTRING()` function allows us to extract parts of a string.


``` java
SUBSTRING(String, Position) # Here, we select our string and the position from which we will take the substring.
```

**Example:**

``` java
SELECT SUBSTRING('softuni.org', 2);
```

**Output**:

```
oftuni.org
```

The second way of using our `SUBSTRING()` is:

``` java
SUBSTRING(String, Position, Length) # We pass in the index at which our result will start to the index at which it will finish.
```

**Example**:

``` java
SELECT SUBSTRING('softuni.org', 1, 3);
```

**Output**:

```
sof
```

We can use the `SUBSTRING()` method this way too:

``` java
SUBSTRING(String FROM Position FOR Length) # This way, we can choose the position from which we want to 
 # start making the substring and for what length.
```

**Example:**

``` java
SELECT SUBSTRING('softuni.org' FROM 2 FOR 5);
```

**The output will be:**

```
ouftun
```

[/slide]


[slide hideTitle]

# Problem with Solution: Find Book Titles - TODO: Add Tests

**Here is a link to the** [resources](https://videos.softuni.org/resources/java/java-mysql/04.Built-In-Functions-And-Data-Aggregation-Lab.zip) **for this task.**

Create an SQL query to find **books, which titles start with "The".** 

**Order the result by id.** 

## Example:

| Title |
| --- |
| The Mysterious Affair at Styles |
| The Big Four |
| The Murder at the Vicarage |
| The Mystery of the Blue Train |
| The Ring |
| ..... |

[/slide]

[slide hideTitle]

## The REPLACE() Function


Now, let us take a look at the `REPLACE()` function in MySQL:

The `REPLACE()` function allows us to replace all occurrences of a substring with a string.


It is crucial to know that this method performs on a **case-sensitive** match.

``` java
REPLACE(String, Pattern, Replacement) # Where "String" is our field from the table.
 # "Pattern" is the string, which we need to replace
 # "Replacement" is our replacement string 
```

**Example:**

``` java
SELECT REPLACE('aaa.softuni.org','a','w'); # In this example, "a" will be replaced with "w"
```

**Output**:

```
www.softuni.org
```

Using this method, we can **replace entire words**

**Example**:

``` java
SELECT REPLACE('We can replace the word blood with a different symbol or word.', 'blood', '*****') 
# First, we have our text
# Then, we write the word we need to replace
# And finally, we pass in the replacement symbols or characters
```

**Output**:

```
We can replace the word ***** with a different symbol or word.
```

[/slide]

[slide hideTitle]

# Problem with Solution: Replace Titles - TODO: Add Tests

Create an SQL query to find books, which titles **start with the word "The" and replace the word with 3 asterisks.**

Extract data about the updated titles.

**Order the result by the id column**.

[/slide]

[slide hideTitle]

## The LTRIM() & RTRIM() Functions

The **LTRIM()** and **RTRIM()** functions remove the space character from a string passed as an argument.

We can use the function like this:

``` java
LTRIM(String)
RTRIM(String)
```

Let us take a look at this simple example:

``` java
SELECT LTRIM(' SoftUni rocks!')
```

The `LTRIM()` function will trim the spaces at the beginning of the string, before "SoftUni rocks!", and the **output** will be:

``` 
SoftUni rocks!
```

The same principle is valid for the `RTRIM()` function, but this time it will remove the trailing spaces at the end after the text.

``` java
SELECT RTRIM('SoftUni rocks!' )
```

**Output**:

```
SoftUni rocks!
```

[/slide]

[slide hideTitle]

## The CHAR_LENGTH() & LENGTH() Functions

The `CHAR_LENGTH()` function will return the length of the provided string. 

``` java
SELECT CHAR_LENGTH('Let us count the characters in this sentence');
# This will count the whitespaces too
```

**Output**:

```
44
```

The `LENGTH()` will return the **same result** from the input above:

It is important to know that a **multi-byte character will count as a single character**.


If our string **contains five two-byte characters**, our `CHAR_LENGTH()` function will return **5**, but our `LENGTH()` will return **10**.


**Example**:

``` java
SELECT LENGTH('§'); # Returns 2
SELECT CHAR_LENGTH('§'); # Returns 1
```

As we see here, the `LENGTH()` function will return a result of **2** and the `CHAR_LENGTH()` a return of **1**.

[/slide]

[slide hideTitle]

# The LEFT() & RIGHT() Functions

The `LEFT()` and `RIGHT()` functions return characters from the **beginning** or from the **end** of a string.

**Syntax**:

``` java
LEFT(String, Count)
RIGHT(String, Count)
```

**Example**:

``` java
SELECT LEFT('Testing Left Function', 5); # This syntax returns the first five characters from the left side of our string.
```

**Output**:

```
Testi
```

Similarly, the `RIGHT()` function will return the first characters from the right in the provided string:

**Example**:

``` java
SELECT RIGHT('Testing Left Function', 5);
```

**Output**:

```
ction
```


[/slide]

[slide hideTitle]

## The LOWER() & UPPER() Functions

The `LOWER()` function converts all characters in the provided string to **lowercase** letters.

**Example**:

``` java
SELECT LOWER('SOFTUNI DB COURSE');
```

**Output**:

```
softuni db course
```

Similarly, the `UPPER()` function to convert all characters to **uppercase** letters.

**Example:**

``` java
SELECT UPPER('this is an uppercase string');
```

**Output:**

```
THIS IS AN UPPERCASE STRING
```

[/slide]

[slide hideTitle]

## The REVERSE() & REPEAT() Functions

The `REVERSE()` function allows us to reverse the order of all characters in the provided string.

**Example**:

``` java
SELECT REVERSE('softuni'); # This will reverse the characters in the "softuni" string
```

**Output**:

```
inutfos
```

The `REPEAT()` function allows us to repeat a string a specified number of times.

**Example**:

``` java
SELECT REPEAT('softuni ', 3); # This will repeat softuni with the whitespace after exactly 3 times
```

**Output**:

```
softuni softuni softuni 
```
[/slide]

[slide hideTitle]

## The LOCATE() & INSERT() Functions

`LOCATE()` function in MySQL lets us locate a specific pattern (substring) in our string.

The function performs a **case-insensitive** search.

**Syntax**:

``` java
LOCATE(Pattern, String, [Position]) # Where the [Position] argument is optional. If omitted, it defaults to 1. 
 # The first position in our string is 1.
```

**Example**:

``` java
SELECT LOCATE('st','teststring');
```

The following **output** will be:

```
3
```

The `INSERT()` function allows us to insert substring at a specific position.

**Syntax**:

``` java
INSERT(String, Position, Length, Substring) # The Length parameter indicates the count of characters that will be deleted from the start of the given Position.
```

**Example**:

``` java
SELECT INSERT('SoftuniTestString', 2, 4, ' insert ');
```

**Output after executing:**

```
S insert niTestString
```
[/slide]
