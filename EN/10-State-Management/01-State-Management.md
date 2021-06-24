# State Management

[slide hideTitle]

# Introduction to NgRx

03-04-introduction-to-state-management

The **NgRx** framework is created for building **reactive Angular applications**.

It provides a selection of **libraries** for **controlling application state** and the **flow of data** throughout the application.

When building an Angular application, the state is typically handled by a number of different services.

As our project grows, state management can become a big problem - keeping track of changes is hard.

In the case of a problem, debugging becomes almost impossible.

NgRx solves this issue by handling state in a single object, making modification a lot easier.

Inspired by **Redux**, **NgRx Store** makes working with complex data **easier** for us to **manage** and **test**.

[/slide]


[slide hideTitle]

# NgRx Packages

05-NgRx-Packages

**NgRx libraries** are divided in **four main categories**:

## State Management

- **Store** - a state management solution made for Angular:
  * built on the Redux principles, it leverages the power of RxJS
  * embraces the use of Observables

- **Effects** - provides a side effect model to NgRx Store:
  * effects are Observables that use Actions both as a source and a destination
  * they can subscribe and publish to the Action Stream

- **Router Store** - provides bindings for connection between Angular Router and NgRx Store

- **Entity** - a library that provides an API for collection management

- **ComponentStore** - used for managing local state

## Data Supervision

- **Data** - simplifies managing entity data
  * less boilerplate code as a result
  * extends the Entity package

## View Control

- **Component** - enables creating fully reactive Angular applications:
  * allows for more control over the rendering process of components
  * currently in an experimental phase

## Developer Tooling

- **Store Devtools** - provides developer tools for `@ngrx/store`

- **Schematics** - a scaffolding library that provides CLI commands for generating constructs:
  * all the other libraries must be installed first


[/slide]


[slide hideTitle]

# State Management Lifecycle

06-State-Management-Lifecycle

The three most important pieces of the **state management lifecycle** are the **store**, **actions** and **reducers**.

The **store** holds the application **state** in a single **object** and **applies changes** to it when an action is **dispatched**.

**Actions** are responsible for **sending data** to a **reducer**.

**Reducers** take the **last action that has been dispatched** and **compare** it to the current state, **updating the state** when needed.

For example, let us say that the user clicks on a **button**. 

When the click event occurs, we want to change a display **value** of a **sidebar** component - either show it or hide it.

However, the two UI components are stored **separately**.

NgRx **handles** and store these state changes for us in a **singular** state object.

As soon as the button has been clicked, its encapsulating component dispatches an **action**.

This action is sent to the **reducer**.

The reducer takes the **current** state and returns a new one, depending on the action provided.

Keep in mind that state is **immutable** - the reducer always returns a **new state**.

[/slide]