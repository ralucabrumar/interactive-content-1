# Introduction to JavaScript

[slide hideTitle]

# Dynamic Programming Language

[video src="https://videos.softuni.org/hls/Java/JS-Fundamentals/EN/00-Syntax-Statements-Functions/js-advanved-syntax-functions-and-statements-3-4-Introduction-to-java-script-dynamic-programming-language-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

JavaScript is what is known as a **dynamic programming language**.

This type of language is more flexible compared to **static programming languages** because the programmer can pass parameters during the runtime of the program, and they do not need to define the type of variable in advance.

This is why JavaScript is also called a **dynamically typed** language.

We can essentially use one variable to store many different types of values.

In comparison, in **statically typed** languages such as Java or C#, you are typically forced to declare your variable types in advance. 

When working with **static programming languages** and you use one variable to store text, you will not be able to override the same variable with numerical data, and attempting so will result in an error.

```js
string lastPlaceVisited = "Jeffrey's Bar";

//The below results in an error in statically typed languages

lastPlaceVisited = 777;
```

In JavaScript, you can change the **type** of a variable, and you can also add **new properties** or **methods** to an object dynamically (while the program is running).

```js live
var lastPlaceVisited = "Mr. Magoo's Emporium";

console.log(lastPlaceVisited);

lastPlaceVisited = 13;

console.log(lastPlaceVisited);
```

If you run the code from the example above, you will see that JavaScript **accepts** the assignment of a numerical value even though the **lastPlaceVisited** variable was first used for storing text.

Ultimately, it is the programmer's **responsibility** to **ensure** that user input **does not cause** errors in the application and is handled correctly, regardless of type.

[/slide]

[slide hideTitle]
# Data Types

[video src="https://videos.softuni.org/hls/Java/JS-Fundamentals/EN/00-Syntax-Statements-Functions/js-advanved-syntax-functions-and-statements-5-data-types-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

We can divide the types of data available in JavaScript into two groups - **primitives** and **reference** types. 

A variable that is assigned a **primitive data type value**, holds the value of the data **directly**, and contains no additional properties or methods.

Variables that contain **Reference** data such as **Objects** actually hold references to the memory locations of the data stored in them.

Here is a table containing the s**even primitive data types** in JavaScript.

| **Type** | **Description** |
| --- | --- |
| String | Represents text |
| Number | Represents numeric values |
| Boolean | A logical data type that contains either `true` or `false` |
| undefined | Assigned automatically to variables at the time of their declaration |
| null | Represents the intentional absence of any object value  |
| BigInt | Used for working with very big integers, and it is limited by the amount of memory available in the system |
| Symbol | Represents a unique identifier. Each time a symbol value is created, an anonymous unique value is created. |

[/slide]

[slide hideTitle]
# Installing Node.js and Visual Studio Code

[video src="https://videos.softuni.org/hls/javascript-basics/00.Introduction-to-Programming/EN/interactive-JS-PB-intorduction-to-programming-20-21-22-Installing-NodeJS-and-Visual-Studio-Code-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

We need **Node.js** so that we can execute JavaScript code outside of a browser.

* Server-side JS runtime

[image assetsSrc="intro-to-programming-3.png" /]

You can download [Node.js](https://nodejs.org/en/download/).

[image assetsSrc="intro-to-programming-install-nodejs-1.png" /]

Select your operating system and go on with installing.
[image assetsSrc="intro-to-programming-install-nodejs-2.png" /]

Let us continue with the installation of the integrated environment **Microsoft Visual Studio Code**.

Installing later versions of Visual Studio Code should be very similar.

[Visual Studio Code](https://code.visualstudio.com/download) (VS Code) is distributed freely by Microsoft.

The next lines describe in detail the steps for the installation of Visual Studio Code. 

After we download the installation file and start it, the following screen will appear:
[image assetsSrc="intro-to-programming-install-vscode-1.png" /]

We press the `[Next]` button and we will see the screen below:
[image assetsSrc="intro-to-programming-install-vscode-2.png" /]

We can choose a destination location or leave the default one. Then we press the `[Next]` button again.
[image assetsSrc="intro-to-programming-install-vscode-3.png" /]

Next, we have to specify a name for the program folder that will be created in the Start Menu. 

The next step is to put check marks on these tasks:
[image assetsSrc="intro-to-programming-install-vscode-4.png" /]

VS is now ready for installation. We press the `[Install]` button. This is everything.
[image assetsSrc="intro-to-programming-install-vscode-5.png" /]

Installation of Visual Studio begins, and a screen like the one below will appear:
[image assetsSrc="intro-to-programming-install-vscode-6.png" /]

After Visual Studio is installed, the following screen will appear. Press the `[Launch]` button to start VS.
[image assetsSrc="intro-to-programming-install-vscode-7.png" /]

Upon **starting Visual Studio Code**, the main view is displayed. 

[image assetsSrc="intro-to-programming-install-vscode-8.png" /]

We are ready to start using Visual Studio Code.
[/slide]

[slide hideTitle]

# Identifiers

[video src="https://videos.softuni.org/hls/Java/JS-Fundamentals/EN/00-Syntax-Statements-Functions/js-advanved-syntax-functions-and-statements-6-Identifiers-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Identifiers are **sequences** of characters in the code used to **identify** a particular variable, function, or property.

When you are giving a name to a variable, you are **assigning** it a unique identifier.

Here are some rules that apply to identifiers:

- Identifiers are **case-sensitive** 
- Can contain unicode characters such as **letters**, **$**, **_** and **digits from 0-9**
- Identifiers **cannot start with a digit**

Valid identifiers:
- `var _month = "January"`
- `function $doSomething()`
- `let moneyAmount = 131`


Invalid identifier:
- `var 2price`

Identifiers are not the **same as strings** because a string **contains data**, while identifiers are **considered** part of the code. 

For example, "**Good morning**" stored in a string called **greeting** is data of type string, while greeting is the **name of the string** - the identifier.

[/slide]

[slide hideTitle]

# Variable Values

[video src="https://videos.softuni.org/hls/Java/JS-Fundamentals/EN/00-Syntax-Statements-Functions/js-advanved-syntax-functions-and-statements-7-8-variable-values-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Every variable **stores** a value inside it. 

Primitive values are stored **directly in the variables**, while variables that are assigned non-primitive values, hold **references** to those values.

A variable that has been declared with **no value assigned to it** will contain a value of `undefined` by default.

We can demonstrate it with some code:

```js live
let weight;
console.log(weight);
```

Printing the value of **weight** to the console shows **undefined**.

JavaScript also has a value for variables that have never been declared:

```js live
console.log(topScore);
```

Variables that are not defined at all are considered `Undeclared` and trying to access such variables results in a **Reference Error**.

In summary variables can contain:
- Primitive data values
- Non-primitive data values (references in memory)
- Undeclared
- Undefined 

## Declaring Variables

We can use `let`, `const`, or `var` for declaring variables.

Each of them serves a different purpose.

**let** is used for declaring **reassignable** variables and is **block-scoped**. 

**Reassignable** means that you can change the value of the variable **after** assigning.

Block-scoped means that the variable will be **accessible only inside the block where it is declared.** 

```js live
{
    let profession = 'Lawyer';
    console.log(profession);
}

console.log(profession);
```

The above example shows the concept of **block-scope** as the **profession** variable is not available outside the code block; attempting to log it to the console results in an error.

**const** is used for variables holding constant values that are not likely to change over time. 

Const variables **cannot be assigned new values**, and once set, attempting to change the value results in an **TypeError**.

```js live
const daysInWeek = 7;
daysInWeek = 2; //Type Error
```

The **var** is similar to **let** but it is **not block-scoped**, meaning that the variable will be available within the whole function where it is declared.

```js live
{
    var profession = 'Lawyer';
    console.log(profession);
}

console.log(profession);
```

Last time we attempted this, we could not log the value of **profession** but since we used **var** which has a bigger scope, this works fine.

Be careful with using **var** as it might result in unexpected behavior.

Declaring variables with **let** is generally considered safer as their scope is much more limited.

**Var** is **function-scoped** and will be available only within the function it was defined in.

```js live
function announceProfession() {
    var profession = 'Software Architect';
    console.log(profession);
}

console.log(profession);
```

The above results in a **ReferenceError** because **var** is **function-scoped**.

[/slide]

[slide hideTitle]

# Variable Scopes

[video src="https://videos.softuni.org/hls/Java/JS-Fundamentals/EN/00-Syntax-Statements-Functions/js-advanved-syntax-functions-and-statements-9-variable-scopes-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

There are a few different types of variable scopes in JavaScript.

Let us see three of them: 

- **Global scope** - this is the area outside of any function or block of code; there is only one global scope in the program

```js live
var subject = 'Applied Physics'
console.log(subject); //Applied Physics

function getSubject() {
    console.log(subject); //still accessible
}

getSubject();  
```

- **Function scope** - this is the code area within a function declaration; function-scope variables are available only within the function declared

```js live
function displayName() {
    var name = 'Leon';
    console.log('functions-scoped: ', leon);
}

displayName();
console.log(name); //error
```

In the above example, logging the **name** from inside the function works, but trying to access it outside of the function scope results in an error.


- **Block scope** - the area of code within a block of code signified by a pair of curly braces `{ }`

```js live
function checkStatus() {
    if (true) {
        let status1 = 'DISCONNECTED';
        var status2 = 'OK';
        const status3 = 'DENIED';

    }
    //console.log(status1);
    console.log(status2);
    //console.log(status3);
}

checkStatus();
```

Run the code above and you should see the value of **status2** printed to the console.

This works because **var** is function scoped.

Now remove the comments for **status1** or **status3** (the `//` in front of the `console.log()` function), and run the code again.

This immediately causes an error because **let** and **const** are both block scoped and can only be used within the if code block. 

[/slide]

[slide hideTitle]

# Dynamic Typing

[video src="https://videos.softuni.org/hls/Java/JS-Fundamentals/EN/00-Syntax-Statements-Functions/js-advanved-syntax-functions-and-statements-10-dynamic-typing-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Because JavaScript is a dynamically typed language, the declared variables are **not directly associated** with a particular value type.

As long as you did not declare a variable with the **const** keyword, any variable can be assigned and re-assigned 
different values of any type.

```js live
let myVariable = 'Gone with the wind'; //String
console.log(myVariable);

myVariable = 15; //Turns into a number
console.log(myVariable);

myVariable = false; //And now a boolean value
console.log(myVariable);
```

Just because you can store **any type of value** in a single variable, it does not mean you **should**.

Most of the time this is considered a **bad practice** and should be **avoided** as each variable should serve one purpose.


[/slide]