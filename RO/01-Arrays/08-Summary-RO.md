[slide hideTitle]
# Summary

## In this lesson you learned:

- Arrays are list-like objects

```js
let furits = ['Orange', 'Peach', 'Grapes']
```

- Elements are accessed using their index number
```js
let furits = ['Orange', 'Peach', 'Grapes']

console.log(fruits[0]) // Orange
```
- Mutator methods - methods that change the original array
   - `array.pop()`, `array.push()`, `array.shift()`, `array.unshift()`, `array.Splice()`, `array.fill()`, `array.reverse()`, `array.sort()`
- Accessor methods - methods that return new array
  - `array.join()`, `array.IndexOf()`, `array.concat()`, `array.includes()`, `array.slice()`
- Looping through arrays 
```js
let furits = ['Orange', 'Peach', 'Grapes']
furits.forEach(fruit => { console.log(fruit); });

```
- Nested arrays
```js
let arr = [
    [4, 6, 3, 0],
    [2, 1, -2],
    [-5, 17],
    [7, 3, 9, 12]
];

```

## In the next lesson, you will learn:

- Objects
  - Object and Properties
  - Looping Through Objects
- JSON
- Classes
  - Definition
  - Constructor
  - Fields

[/slide]