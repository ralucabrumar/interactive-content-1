
# Nested Arrays

[slide hideTitle]

# Nested Arrays in JavaScript

The arrays we have been using so far have only held **one column** of data.

But we can set up an array to hold more than one column, called **multi-dimensional arrays** or matrices.

As an example, think of a **spreadsheet** with rows and columns.

If you have 6 rows and 5 columns then your **spreadsheet** can hold 30 numbers, which is a classical example of a **matrix**.

It might look like this:

[image assetsSrc="Java-Advanced-Multidimensional-Arrays-1.png" /]

There is also another type of **multi-dimensional arrays**, called a **jagged array**, where every row has a **different** number of elements:

[image assetsSrc="java-js-adv-arrays-03.png" /]

In this example, there is an array of four arrays (**jagged array**), and each row has a different number of elements.

JavaScript representation of this example is:

```js live
let arr = [
    [4, 6, 3, 0],
    [2, 1, -2],
    [-5, 17],
    [7, 3, 9, 12]
];


console.log(arr[2][0])
```

[/slide]

[slide hideTitle]

# Looping Through a Nested Array

**Example:**

```js live
let arr = [[4, 5, 6],
           [6, 5, 4],
           [5, 5, 5]];

arr.forEach(printRow);

function printRow(row){
    console.log(row);
    row.forEach(el => console.log(el));
}
```
A **matrix** can be print using **forEach** loop, where an argument (current row) is passed to a function.

Another forEach is **used** to iterate through every **element** from the **row**, and print it to the **console**.

[/slide]

[slide hideTitle]

# Problem: Diagonal Sums

[code-task title="Diagonal Sums" taskId="java-path-js-advanced-arrays-Diagonal-Sums" executionType="tests-execution" executionStrategy="javascript-code" requiresInput]
[code-editor language=javascript]

```
function diagonalSums(input){
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

Write a function that finds the sum of the two diagonals in a square matrix. 

The **input** comes as **array of arrays**, containing number elements (2D matrix of numbers). 

The **output** is printed to the console on a single line, separated by space. First, print the sum of the main diagonal, then the sum of the secondary diagonal. 

## Examples
| **Input** | **Output** |
| --- | --- |
|biggerHalf([ [ 20, 40 ], [ 10, 60 ] ]) | 80 50  |
|biggerHalf([ [ 3, 5, 17 ], [ -1, 7, 14 ], [ 1, -8, 89 ] ]) | 99 25   |

[/task-description]
[code-io /]
[tests]
[test]
[input]
biggerHalf([ [6 45], [1 17] ])
[/input]
[output]
23 46
[/output]
[/test]
[test]
[input]
biggerHalf([ [10] ])
[/input]
[output]
10 10
[/output]
[/test]
[test]
[input]
biggerHalf([ [54 123 130 63], [51 181 112 35], [47 35 110 77], [14 106 156 117] ])
[/input]
[output]
462 224
[/output]
[/test]
[test]
[input]
biggerHalf([ [-8 13], [22 8] ])
[/input]
[output]
0 35
[/output]
[/test]
[test]
[input]
biggerHalf([ [20 40], [10 60] ])
[/input]
[output]
80 50
[/output]
[/test]
[test]
[input]
biggerHalf([ [3 5 17], [-1 7 14], [1 -8 89] ])
[/input]
[output]
99 25
[/output]
[/test]
[/tests]
[/code-task]
[/slide]