# JavaScript Object Notation (JSON)

[slide hideTitle]
# What is JSON?

JSON, short for **JavaScript Object Notation**, is a **text-based** format for data exchange.

It is **language independent**, although it is most often used in the context of JavaScript-based projects, such as websites and single-page applications.

JSON is a method of storing information in an **organized** and easily **understandable** approach. 

```js
{
  "posts": [
    { "id": 1, "title": "JavaScript is Awesome", "author": "michaelp_95" },
    { "id": 2, "title": "How to Set Up Windows 10", "author": "jacob17" },
    { "id": 3, "title": "Why I Think Java is Great for Beginners", "author": "jane_garcia" },
  ]
}
```

The syntax of JSON closely resembles that of a JavaScript **object** - it consists of **key-value** pairs, and can serve as a **representation** of all JavaScript data types, with the exception of functions.

Similarly to XML, it can be used to store data in a **hierarchical** order.

[/slide]

[slide hideTitle]
# Syntax Rules

The following snippet illustrates a typical **JSON** response from a server:

``` js
{
    "id": 98953,
    "name": "Glenna Miller",
    "username": "glennar57",
    "email": "glenna_r@gmail.com",
    "favoriteNums": [4, 82, 39, 174],
    "friendList": {
        "73827": "Logan Pearson",
        "27834": "Alexandra Walters",
        "93421": "Nathan Adams"
    }
}
```

The first thing you might notice is that every data entry is a **key-value** pair.

These pairs are enclosed in curly braces `{}` - the syntax used to **define** a JSON.

All keys, as well as string values, are in **double quotes** - JSON **does not** support single quotes.

The values are **separated** from their keys by using a colon - `:`.

Similarly to JavaScript, **arrays** are held in square brackets, and **objects** - in curly braces.

[/slide]

[slide hideTitle]
# Parsing from Strings

JSON is often used for **reading data from a server**, and using the response to **render** an interface on the client's browser.

To do so, we have to **convert** the **JSON** response into a JavaScript **object** using the `JSON.parse()` method.

```js live
let car = '{"make":"Renault","model":"Clio","colour":"grey"}';  

let data = JSON.parse(car);  

console.log(data);
```

In this example, we receive a JSON string - `car`, which we then **parse** to a `data` object.

[/slide]

[slide hideTitle]
# Converting to String

The `JSON.stringify()` method converts a JavaScript value to a JSON string representation.

It can accept objects, as well as arrays.

```js live
let notebook = {
    pages: '120',
    size: 'A4',
    manufacturedBy: 'Rocketbook',
};

let cities = ['London', 'Bucharest', 'Paris']

let notebookData = JSON.stringify(notebook);
let cityData = JSON.stringify(cities);

console.log(notebookData);
console.log(cityData);
```

As evident by the output, `stringify` returns a ready for transfer **JSON** string.

[/slide]

[slide hideTitle]
# Problem with Solution: From JSON to HTML Table

[code-task title="From JSON to HTML Table" taskId="java-path-js-advanced-objects-and-classes-from-json-to-html-table" executionType="tests-execution" executionStrategy="javascript-code" requiresInput]
[code-editor language=javascript]
```
function fromJSONToHTMLTable(studentData){
    // Write your code here
}
```
[/code-editor]
[code-adapter]
```
function adapter(input, code) {
    let inputParams = /\((.+)\)$/.exec(input)[1];
    inputParams = eval(`[${inputParams}]`);
    return code(...inputParams);
}
```
[/code-adapter]
[task-description]
# Description

You are tasked with creating an HTML table of students and their scores. 

You will receive a single string representing an **array of objects**. 

The table’s headings should be equal to the **object’s keys**, while **each of the object’s values** should be a **new entry** in the table. 

Any **text values** in an object should be **escaped** in order to avoid introducing dangerous code into the HTML.  
 
## Input 
The **input** comes a **single string argument** (the array of objects). 

## Output 
The **output** should be printed to the console – for each **entry row** in the input, print the **object representing it**. 

## Note: 
Object’s **keys** will always be the **same**. Check more information for the **HTML Entity** [here](https://developer.mozilla.org/en-US/docs/Glossary/Entity). 

## HTML 
You are **provided** with an **HTML file** to test your table in the **browser**:

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>FromJSONToHTMLTable</title>
  <style>
    table,
    th {
      border: groove;
      border-collapse: collapse;
    }

    td {
      border: 1px solid black;
    }

    td,
    th {
      padding: 5px;
    }
  </style>
</head>

<body>
  <div id="wrapper">
  </div>
  <script>
    function fromJSONToHTMLTable(studentData) {
      // Write your code here
    }
    window.onload = function () {
      let container = 
        document.getElementById('wrapper');
      container.innerHTML = 
        fromJSONToHTMLTable(['input goes here']);
    };
  </script>
</body>

</html>
```

## Submission

Submit **only** the `fromJSONToHTMLTable` function.


## Example

### Input

`fromJSONToHTMLTable('[{"Name":"Peter <div>-a","Age":20,"City":"London"}, {"Name":"George","Age":18,"City":"Liverpool"}, {"Name":"Tom","Age":18,"City":"Manchester"}]')`

### Output

```html
<table> 
   <tr><th>Name</th><th>Age</th><th>City</th></tr> 
   <tr><td>Peter &lt;div&gt;-a</td><td>20</td><td>London</td></tr> 
   <tr><td>George</td><td>18</td><td>Liverpool</td></tr> 
   <tr><td>Tom</td><td>18</td><td>Manchester</td></tr> 
</table> 
```

[/task-description]
[code-io /]
[tests]
[test open]
[input]
fromJSONToHTMLTable('\[\{"Name":"Peter \<div\>-a","Age":20,"City":"London"\},\{"Name":"George","Age":18,"City":"Liverpool"\},\{"Name":"Tom","Age":18,"City":"Manchester"\}\]')
[/input]
[output]
\<table\>
   \<tr\>\<th\>Name\</th\>\<th\>Age\</th\>\<th\>City\</th\>\</tr\>
   \<tr\>\<td\>Peter &lt;div&gt;-a\</td\>\<td\>20\</td\>\<td\>London\</td\>\</tr\>
   \<tr\>\<td\>George\</td\>\<td\>18\</td\>\<td\>Liverpool\</td\>\</tr\>
   \<tr\>\<td\>Tom\</td\>\<td\>18\</td\>\<td\>Manchester\</td\>\</tr\>
\</table\>
[/output]
[/test]
[test]
[input]
fromJSONToHTMLTable('\[\{"Name":"Tomatoes & Chips","Price":2.35\},\{"Name":"J&B Chocolate","Price":0.96\}\]')
[/input]
[output]
\<table\>
   \<tr\>\<th\>Name\</th\>\<th\>Price\</th\>\</tr\>
   \<tr\>\<td\>Tomatoes &amp; Chips\</td\>\<td\>2.35\</td\>\</tr\>
   \<tr\>\<td\>J&amp;B Chocolate\</td\>\<td\>0.96\</td\>\</tr\>
\</table\>
[/output]
[/test]
[test]
[input]
fromJSONToHTMLTable('\[\{"X":5,"Y":7\},\{"X":2,"Y":4\},\{"X":-5,"Y":13\},\{"X":4.44,"Y":8\},\{"X":-10,"Y":-120.12\}\]')
[/input]
[output]
\<table\>
   \<tr\>\<th\>X\</th\>\<th\>Y\</th\>\</tr\>
   \<tr\>\<td\>5\</td\>\<td\>7\</td\>\</tr\>
   \<tr\>\<td\>2\</td\>\<td\>4\</td\>\</tr\>
   \<tr\>\<td\>-5\</td\>\<td\>13\</td\>\</tr\>
   \<tr\>\<td\>4.44\</td\>\<td\>8\</td\>\</tr\>
   \<tr\>\<td\>-10\</td\>\<td\>-120.12\</td\>\</tr\>
\</table\>
[/output]
[/test]
[test]
[input]
fromJSONToHTMLTable('\[\{"Name":"\<script\>alert('Hacked');\</script\>","Age":20,"City":"'Vinkel Town' Pernik & Co."\}\]')
[/input]
[output]
\<table\>
   \<tr\>\<th\>Name\</th\>\<th\>Age\</th\>\<th\>City\</th\>\</tr\>
   \<tr\>\<td\>&lt;script&gt;alert(&\#39;Hacked&\#39;);&lt;/script&gt;\</td\>\<td\>20\</td\>\<td\>&\#39;Vinkel Town&\#39; Pernik &amp; Co.\</td\>\</tr\>
\</table\>
[/output]
[/test]
[/tests]
[/code-task]
[/slide]