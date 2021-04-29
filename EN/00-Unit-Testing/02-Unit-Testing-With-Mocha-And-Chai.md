# Unit Testing with Mocha and Chai

[slide hideTitle]

# What are Mocha and Chai?

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/01.JS-Applications-Unit-Testing/EN/interactive-js-apps-unit-testing-8-9-10-mocha-and-chai-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]


## Mocha

**Mocha** is a feature-rich JavaScript test framework that runs on Node.js or in the browser, making asynchronous testing simple and easy to do.

Mocha tests run sequentially, allowing for flexible and accurate reporting, while mapping uncaught exceptions to the correct test cases. 

Mocha provides common testing functions including **it**, **describe**, and the main function that runs tests.

Mocha is usually used together with **Chai**.


This is the syntax of a Mocha unit test:

```js
describe('title', function () {
    it('title', function () { ... });
});
```

Mocha utilizes several hooks to run tests:

| **Name**  | **Description** |
| --- | --- |
| describe() | Used for grouping the contents of the unit test, you can nest describe() hooks. |
| it() | Contains a single test case. |
| before() | Runs once before the first it() hook in a given describe() |
| beforeEach() | Runs before each it() hook |
| after() | Runs after the first it() hook |
| afterEach() | Runs after each it() hook |


Let us see an example with the built-in assertions library. There are and two tests grouped together.

```js
var assert = require('assert');

// Creating a test group called "MathOperations"
describe('MathOperations', function() {
    // First test describing what we are testing
    it('Multiplying 2*2 should equal 4', function(){
      assert.equal(4, 2*2);
    });
    // Second test
    it('(0+2)*2 should be equal to 4', function(){
      assert.equal(4, (0+2)*2);
    });
});
```



Here is a [link](https://www.mochajs.org/) to the Mocha.Js documentation. 

## Chai

**Chai** is an **assertion library** that can be paired with any JavaScript testing framework.

It allows the usage of a lot of different assertions such as `assert.equal`, `asset.typeOf` and `assert.lengthOf`.

Before using **Chai**, we need to import the required module using the following keyword: `require`.

This is done on the first line of the code: `let assert = require("chai").assert;`

Chai provides three different styles of writing tests by using one of the following:
- Should
- Expect
- Assert

We will take a closer look at **Assert** and **Expect** in the next slides.

[/slide]


[slide hideTitle]
# Chai Expect

Here is an example unit test using **expect**:

```js
let assert = require('chai').expect;
describe('ComparingStrings', function() {
    it('The two strings should be equal', function() {
        expect("string1").to.equal("string2");
    });
});
```

Some of the assertions that are available in the Chai library are:

| **Assertion**  | **Description** |
| --- | --- |
| expect(actual).to.equal(expected) | Compare using `==` (e.g. 2 would be considered equal to "2") |
| expect(actual).to.eql(expected) | Compare using `===` (e.g. 2 is not equal to "2" as they are of different types)  |
| expect(actual).to.deep.equal(expected) | Same as the above one |
| equal(actual).to.be(expected) | Checks the type of the object |
| expect(actual).to.include(expected) | Asserts that the actual object's properties are a subset of the expected object's properties |
| expect(actual).to.be.true | Asserts that the object is strictly true (===). You can also use `.to.be.false`  |


Here is a [link](https://www.chaijs.com/api/bdd) to the Chai.JS documentation on `expect`.

[/slide]

[slide hideTitle]
# Chai Assert

Here is an example of a unit test using **assert**:

```js
let assert = require('chai').assert;
describe('pow', function() {
    it('2 raised to power 3 is 8', function() {
        assert.equal(pow(2, 3), 8);
    });
});
```

Out test group is called "pow". It contains one test checking for the result of an operation.

The test uses `assert.equal()` to determine if the operation is successful (if it is, the test passes).

Some of the assertions that are available in the Chai library are:

| **Assertion**  | **Description** |
| --- | --- |
| assert.equal(actual, expected) | Compare using `==` (e.g. 2 would be considered equal to "2") |
| assert.strictEqual(actual, expected) | Compare using `===` (e.g. 2 is not equal to "2" as they are of different types) |
| assert.deepEqual(actual, expected) | Asserts that `actual` is deeply equal to `expected`. Used for objects, when you want to compare every value of every property|
| assert.typeOf(value, name) | Checks if the given value is of the specified type|
| assert.isTrue(value) | Checks if the given value is `true`. You can also use isNull(), isNotNull, isUndefined(), isDefined(), isFunction(), isObject(), isArray(), isString(), isNumber(), isBoolean() |

We can attach a message to any assertion.

To do so, we add an additional parameter to any of the assertions like this: assert.typeOf(null, 'null', 'This is of type null').

Here is a [link](https://www.chaijs.com/api/assert) to the Chai.JS documentation on `assert`.

[/slide]