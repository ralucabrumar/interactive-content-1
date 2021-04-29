# Common Design Patterns 

[slide hideTitle]
# Factory Pattern

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-11-12-factory-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

The **factory design pattern** is a creational pattern and its purpose is creating objects. 

It is just like an actual factory in real life. 

It **produces** products (objects) based on business requirements. 

The logic of how the products are **manufactured** does not need to be known by the client using the services of the factory. 

New types of objects can be added at any time to the manufacturing process of the factory. 


This pattern is used when:

- The setup of objects requires a high level of complexity

The logic for instantiating objects is **encapsulated** within the factory object and the client **does not need to know** the actual logic to use it.

It calls upon the **factory** and **receives** the created object:

- When you need to **generate** different instances of objects depending on the context

- When working with objects or components that **share the same properties**

- When you need to create a **loosely coupled system**

## When not to use

If applied incorrectly, it can introduce a lot of **unnecessary** complexity into the code. 

Do not use it unless your goal is to create an **interface for object** creation and you need to be able to constantly construct new objects of certain types without exposing the logic to the clients using it.

The creation of new objects is **abstracted behind an interface**, which can cause **problems in unit testing later on** depending on how complex the logic of the factory is.

[/slide]

[slide hideTitle]
# Pros and Cons

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-13-pros-and-cons-of-the-factory-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

|  **Pros** |**Cons**   |
|---|---|
| dynamic object creation   |  can overcomplicate code (too many sub-classes) |
| abstraction   |  can introduce problems with unit testing  |
|+reusability and easier maintenance   |   |

One of the biggest benefits of the **factory pattern** is that we can move the object instantiation logic to a single place in the program, which can make the code easier to support. 

This is the basis behind the **Single Responsibility Principle**.

It also adheres to the **Open/Closed Principle** which states that each software entity should be open for extension but closed for modification. 

This is because you can add new types of features without risking breaking the existing client code.

[/slide]

[slide hideTitle]
# Example

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-14-15-examples-with-the-factory-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Below is an example of how the factory pattern can be used:

We are defining a function called "**Digimon**" which accepts a **name** and a **specialMove** as parameters and prints the name of the digital monster and its special move when `.attack()` is invoked on it. 

```js live
function Digimon(name, specialMove) {
    this.name = name;
    this.specialMove = specialMove;

    this.attack = () => {
        console.log(`${name} attacks with ${specialMove}!`);
    };
}

function DigimonFactory() {
    this.create = function(name, specialMove) {
        return new Digimon(name, specialMove)
    }
}

let digimonFactory = new DigimonFactory();
let digitalMonsters = [];

digitalMonsters.push(digimonFactory.create('Agumon', 'Fire Breath'));
digitalMonsters.push(digimonFactory.create('Botamon', 'Bubble Blow'));

digitalMonsters.forEach((digimon) => {
    digimon.attack();
});
```

In the example above, we have a **digimonFactory** that is used to create new digital monsters. 

We then create an **empty array** and push some digital monsters into it after **creating** them using the factory. 

Finally, we iterate through the collection and **print out the names** and special moves of each monster inside the collection.

[/slide]

[slide hideTitle]
# Decorator Pattern

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-16-17-decorator-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

The **decorator pattern** is a structural design pattern that promotes code reusability and is an alternative to subclassing.

With this pattern, extra responsibilities or behaviors can be **added** to objects during **runtime**, without breaking the code that uses them.

## When to use

- When you need to add a **functionality** to an object either dynamically (during runtime) or statically, without affecting the **behavior** of other objects of the same class

- When extending with subclasses is not practical

## When not to use

The decorators can introduce problems when your code relies on specific types of objects and checks their type. 

For example: 

```js
function Car(make, model, year) {
    this.make = make;
    this.model = model;
    this.year = year;
}

let toyota = new Car('Toyota', 'Corolla', 1998);

function performAction(car) {
    if (toyota instanceof Car) {
        console.log('Do something');
    } else {
        console.log('Do something else');
    }
}

performAction(toyota);
// "Do something"

```

If you were to use a decorator on top of the `Car` object in the above example then the check form **instanceof** would return `false` and the code in the **else** block would be executed, which might not be the intended behavior.

[/slide]

[slide hideTitle]
# Pros and Cons

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-18-pros-and-cons-of-the-decorator-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

|  **Pros** |**Cons**   |
|---|---|
| extend functionality without modifying the objects that you are decorating   | can add too many small objects  |
|add and withdraw responsibilities as needed  | can cause issues when the client relies heavily on the concrete type of components  |
| supports the Open/Closed SOLID principle   | instantiating the components can become more complicated |
[/slide]

[slide hideTitle]
# Example

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-19-20-examples-with-the-decorator-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Here is an example of how the **decorator pattern** works:

```js live
let EbookReader = function(cost, screenSize) {
    this.cost = cost;
    this.screenSize = screenSize;
    this.info = function() {
        console.log(`Cost: ${cost}, Screen size: ${screenSize}`);
    }
}

/*Decorator 1*/
let DecoratedEbook = function(ebookReader, model) {
    this.cost = ebookReader.cost;
    this.screenSize = ebookReader.screenSize;
    this.model = model;
    this.info = function() {
        console.log('Decorated ebook:');
        console.log(`Model: ${this.model}, Cost: ${this.cost}, Screen size: ${this.screenSize}`)
    }
}

let eBook = new EbookReader(100, 7);
let decoratedEbook = new DecoratedEbook(eBook, 'Kindle');


eBook.info();
decoratedEbook.info();
```

The decorator accepts a parameter "**ebookReader**" - the object we want to decorate and a new property **model**. 

In this way, the decorated ebook reader would have an additional property and the `info()` function has been extended accordingly without modifying the original "**EbookReader**" class.

[/slide]


[slide hideTitle]
# Facade Pattern

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-21-22-facade-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

[image assetsSrc="js-application-design-patterns-14.png" /]

The **facade pattern** is used a lot in multi-layered applications where only certain logic and functionality need to be exposed to **different clients**, shielding them from any complex business logic that clients do not need to be concerned with. 

It is also useful in **refactoring** and almost always improves code **usability**.

It is implemented by creating a "**wrapper**" class, **encapsulating** the subsystem. 

The client is only **coupled** to the facade and not to the subsystem(s) behind it.

## Use it when you have 

- A **complex** system and you need a **simple** interface to communicate with it

- A lot of tightly **coupled** code which would require the client to have **extensive** knowledge on how the system works in order to use it


[/slide]

[slide hideTitle]
# Pros and Cons

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-23-pros-and-cons-of-the-facade-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

|  **Pros** |**Cons**   |
|---|---|
|You can **isolate** your code from the **complexity of** a **subsystem** | facade can be coupled to too many objects  |

The facade pattern can reduce complexity when several modules are communicating with each other or when the client needs to use several classes at once.

[/slide]

[slide hideTitle]
# Example

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-24-example-with-the-facade-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Here we are creating a "**ComplaintRegistry**" facade class with a method called "**registerComplaint**".

```js
class ComplaintRegistry {
    registerComplaint(customer, type, details) {
        let registry;
        if (type === 'service') {
            registry = new ServiceComplaints();
        } else {
            registry = new ProductComplaints();
        }
        return registry.addComplaint({
            id,
            customer,
            details
        });
    }
}

```

`ServiceComplaints()` and `ProductComplaints()` are complex subsystems, but the client need not be concerned with their implementation. 

The facade simply takes the **customer**, **type** and **details** and adds the complaint to either the service registry if the type received is **service** or a product complaint is of any other type by invoking **addComplaint** on the registry that was created.

[/slide]


[slide hideTitle]
# Observer Pattern

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-25-26-27-observer-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

This is a pattern, in which an object named **subject** maintains a list of dependant objects and notifies them of any state changes, usually through calling one of their methods. 

The **Observer** pattern facilitates a good object-oriented design and promotes loose coupling.

## Common Participants

[image assetsSrc="js-application-design-patterns-15.png" /]

- **Subject**: contains a collection of observers

It can add or remove observers if needed. 

Implements an interface that allows observed objects to be added or removed - `subscribe()`, `unsubscribe()`. 

Sends notifications to the observers attached to it.

- **Observer**: has an interface that sends updates to objects that need to be notified of a subject's changes of state

## Concept 

[image assetsSrc="js-application-design-patterns-10.png" /]

The concept behind the **observer** pattern is that we have one subject, which can have one or more observers. 

It maintains a collection of observers and notifies them when a change occurs to its state.

Messages to the observers are typically sent using a `notify()` method that loops through the subject's list of observers and inside the loop each observer's **update method** is invoked.

When the observer no longer needs to receive updates from the subject it can be **detached** (removed from the subject's collection).

## When to use

When you have a class that needs to be **monitored** by other classes in the program and they need to be **aware** of any changes in **its state**. 

An example of this would be on websites where you can subscribe to other users.

Your account would be added to their **subscribers** and each time they upload a new video, you would be notified, in effect making your account an Observer.

[/slide]

[slide hideTitle]
# Pros and Cons

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-28-pros-and-cons-of-the-observer-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

|  **Pros** |**Cons**   |
|---|---|
|broadcast **changes** and **updates** | can add unnecessary complexity  |
| new observers can be added to the subject with no modification to its code |  unpredictable order of sending notifications |
| add and remove observers at any time |  |
| **loose coupling** between subject and observer |  |

By using the observer pattern, we introduce **loose coupling** between the subject and its observers. 

The subject is only aware of the collection of observers it maintains but is not concerned with the concrete implementation of the observers.

Changes can be **broadcasted** to any number of observers, although the order, in which the **notifications** are sent, can be unpredictable, which might lead to problems.

[/slide]

[slide hideTitle]
# Example

[video src="https://videos.softuni.org/hls/Javascript/Javascript-Applications/08.JS-Applications-Design-Patterns-and-Best-Practices/EN/Design-Patterns-and-Best-Practices-29-example-of-the-observer-pattern-,1080p,720p,480p,360p,240p,.mp4/urlset/master.m3u8" poster="" /]

Here is a simplified example of the **observer pattern**:

```js
class Observable {
    constructor() {
        this.observers = [];
    }
    subscribe(f) {
        this.observers.push(f);
    }
    unsubscribe(f) {
        this.observers = this.observers.
        filter(subscriber => subscriber !== f);
    }
    notify(data) {
        this.observers.forEach(observer => observer(data));
    }
}

```

We are declaring a class called **Observable**. 

It has a constructor that initializes a collection of **observers**: `this.observers = []`. 

The **subscribe** method is used to add observers to the collection of the observable object. 

The **unsubscribe** method removes (**detaches**) an observer from the subject.

When the `notify(data)` method is called we iterate through the collection of observers collection and **send a notification** to **every single observer** that is currently **subscribed** to the observable object.
[/slide]