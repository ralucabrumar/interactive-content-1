# Mongoose Models

[slide hideTitle]
# Models


Models are constructors compiled from *Schema* definitions.

The *Schema* itself defines the structure of the document.

It may define a property like default values, validators, whereas the **model** provides an interface to the database.

The schema can be compiled using `mongoose.Schema` call:

Let us take a look at the following example:

``` js
const exampleSchema = new mongoose.Schema({
  propString: String,
  propNumber: Number,
  propObject: {},
  propArray: [],
  propBool: Boolean
});
const Model = mongoose.model('Example', exampleSchema);
```

The first thing is to create a new schema that we would define the model properties after that compiling.

When we call `mongoose.model()` on a schema, it **compiles** a ready to use model.


[/slide]

[slide hideTitle]

# Model Methods

Mongoose Models are just JavaScript **object constructors**.

They can have **Methods**.

They use different syntax than plain JS.

``` js
const studentSchema = new mongoose.Schema({…});
studentSchema.methods.getInfo = function() { // Avoid arrow function
   return `I am ${this.firstName} ${this.lastName}`;
};
```

As we see, these methods can be added to a schema.

[/slide]

[slide hideTitle]

# Model Virtual Properties

We can create **Virtual** properties that exist only in the **Mongoose Model**, not in the MongoDB itself.

Virtuals are additional fields for a given model. 

A example is helpful:

``` js
// We define a user schema
var userSchema = new Schema({  
    firstName: String,
    lastName: String
});
// Then compile our model
var User = mongoose.model('User', userSchema);
// Final step is to create a document
var employee = new User({  
    firstName: 'Jason',
    lastName: 'Harris'
});
```

if we want to get the full name of our employee we can concatenate the first and last name manually.

``` js
console.log(mentalist.first + ' ' + mentalist.last); // Jason Harris 
```

This can be done using **virtual fields**. 

This way, we will write name concatenation only once.

Virtual properties have both **getters** and **setters**.

``` js
userSchema.virtual('fullname').get(function() {  
    return this.firstName + ' ' + this.lastName;
});
```

The virtual full name property will print the same output as above:

``` js
console.log(employee.fullname); // Jason Harris
```

We can use setters to manipulate our string.

This example **splits** the passed name at any whitespace.

``` js
userSchema.virtual('fullname').set(function (name) {  
  var split = name.split(' ');
  this.first = split[0];
  this.last = split[1];
});
```

[/slide]

[slide hideTitle]

# Property Validation

Using Mongoose, developers can **define** custom **validations** on their properties.

Validation is defined in the *SchemaType*.

``` js 
studentSchema.path('firstName')
  .validate(function () {
    return this.firstName.length >= 2 
  && this.firstName.length <= 10
}, 'First name must be between 2 and 10 symbols long!') // Error message passed as second parameter
```

Data validation is important. 

That way, we can make sure that "**bad**" data does not get in the application.

**Mongoose** has **built-in** support for data schemas, and the automatic validation of data when it is persisted.

**Mongoose validators** are easy to configure.

[/slide]

[slide hideTitle]

# Exporting Modules

Having all model definitions in the **main** module is not good practice.

That is the reason Node.js has **modules** in the first place.

``` js
const mongoose = require('mongoose');
const studentSchema = new mongoose.Schema({
   firstName: { type: String, required: true },
   lastName: { type: String, required: true },
   facultyNumber: { type: String, required: true, unique: true },
   age: { type: Number }
});

module.exports = mongoose.model('Student', studentSchema);
```

We can put each **model** in a different **module** and **load** all models at the start of our program.

``` js
const Student = require('./models/Student');
```

[/slide]

[slide hideTitle]

# Mongoose: Demo

//MongoDB-Demo-2



[/slide]