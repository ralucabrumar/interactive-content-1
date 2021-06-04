# NgRx

[slide hideTitle]

# NgRx Store

07-08-NgRx-and-ngrx-store

The `@ngrx/store` library is a **state management tool** that implements the **Redux** pattern using RxJS **Observables**.

It stores all of our application **data** in a **single immutable object**, called the **Store**.

The store is the **single source of truth** for our application, and as such, it must have an **initial state**.

NgRx Store enforces a **one-way flow of data** and can only be **modified** using **reducers**.

All of this results in **loose coupling**, which **reduces application complexity** and makes **development easier**.


## Installation

Open a command\-line tool in your project's root directory and type:

- `npm install @ngrx/store` if you are using **NPM**.

- `yarn add @ngrx/store` for **Yarn**

## Data Flow

This simple diagram illustrates the **basic flow of data in NgRx**.

[image assetsSrc="state-management(1).png" /]

[/slide]


[slide hideTitle]

# Actions

09-Actions

**Actions** are used to **describe events** that **occur** during the use of an application.

These events include every type of **user interaction**, like **sending a login form**, as well as **API interaction**.

The process of **sending data** is called **dispatching**.

Actions are **dispatched to** and **handled** by **reducers**.

Every **instance of an Action** implements the built-in **Action interface** which has a mandatory `type` property.

The `type` property is a **string**, which describes the **action** that will be **dispatched**.

It contains the **source of the dispatched action between square brackets** and the **event type**:

`[Source] Event Type`

For example, if we want to create an Action for **signing up a user**, the type will look similar to this:

`[Register Page] Signup`

Actions can also contain an optional **payload** of data, like an **email and password** from a **registration form**.

[/slide]


[slide hideTitle]

# Create Actions

10-Create-Actions 

This example shows three actions for **incrementing**, **decrementing** and **resetting** a **Counter Component**.

Now is the time to generate a new Angular project, if you have not already: 

```js
ng generate new ngrx-counter
```

The next step is to generate a `counter` component in Angular CLI:

```js
ng generate component counter
```

Then, we create a new `counter.actions.ts` file in the `app` folder.

```js
import { createAction } from '@ngrx/store';

// An action to increment the counter
export const increment = createAction(
  '[Counter Component] Increment'
)

// An action to decrement the counter
export const increment = createAction(
  '[Counter Component] Increment'
)

// An action to reset the counter
export const increment = createAction(
  '[Counter Component] Increment'
)
```



Inside, we import the `createAction()` method from `@ngrx/store`.

This method accepts the `type` string and a **payload**, if applicable, and **returns an Action object**.

They make the creation of actions less explicit, abstracting the underlying class-based logic from developers.

Action creator functions can also accept another functions as a last argument:

```js
export const registrationSuccess = createAction(
  '[Auth/API] Registration Success',
  (response: Response) => response.user
);
```


[/slide]

[slide hideTitle]

# Reducers

11-Reducers

We use **reducers** to define **how our application state changes**.

They are **responsible** for **handling the transition from one state to another**.

Reducers are **pure functions**, which means that they have **no side effects** - the **return value** is determined only by the **input**.

[/slide]


[slide hideTitle]

# Define a Reducer Function

12-Define-a-Reducer-Function

The **Reducer Function** will be used to **modify the state in the Counter Component** based on the **Аctions** we created earlier:

```js
import { createReducer, on } from '@ngrx/store';
import { increment, decrement, reset } from './counter.actions';
 
export const initialState = 0;
 
const _counterReducer = createReducer(
  initialState,
  on(increment, (state) => state + 1),
  on(decrement, (state) => state - 1),
  on(reset, (state) => 0)
);
 
export function counterReducer(state, action) {
  return _counterReducer(state, action);
}

```

First, we create a new `counter.reducer.ts` file and import `createReducer()` and `on()` from **NgRx Store**.

Then, we import the actions we created earlier from `counter.actions.ts`.

The `createReducer()` function accepts an **initial state** and a number of `on()` function calls for **every action**.

By invoking the `on()` function, we **make associations between actions and state changes**.


[/slide]


[slide hideTitle]

# Add the StoreModule.forRoot

13-Add-the-Store-Module.forRoot

To make the Store **accessible** from **every part of our application** we must go to `app.module.ts` and add `StoreModule.forRoot()` to the imports array:

```js
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// These are the neccessary imports
import { StoreModule } from '@ngrx/store';
import { counterReducer } from './counter.reducer';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule,
    StoreModule.forRoot({ count: counterReducer })],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule { }
```

The `forRoot()` method accepts a **map of key-value pairs** that define our **application state**. 

Here, we pass in an and object with a single `count` property, which stores the `counterReducer`.
[/slide]


[slide hideTitle]

# Create a Counter Component

14-15-Create-a-Counter-Component

Create a new **Counter Component** with **Angular CLI**:

`ng generate component counter`

This command will create a `counter` folder inside `src/app` and will **automatically add the component** to the `declarations` array in `app.module.ts`.

Inside `src/app/counter/`, open `counter.component.ts`.

```js
import { Component } from '@angular/core';
import { Store } from '@ngrx/store';
import { Observable } from 'rxjs';
import { increment, decrement, reset } from '../counter.actions';

@Component({
  selector: 'app-counter',
  templateUrl: './counter.component.html',
  styleUrls: ['./counter.component.css'],
})
export class MyCounterComponent {
  count$: Observable<number>;

  constructor(private store: Store<{ count: number }>) {
    this.count$ = store.select('count');
  }

  increment() {
    this.store.dispatch(increment());
  }

  decrement() {
    this.store.dispatch(decrement());
  }

  reset() {
    this.store.dispatch(reset());
  }
}
```

Inside, add the following imports:

```js
import { Store } from '@ngrx/store';
import { Observable } from 'rxjs';
import { increment, decrement, reset } from '../counter.actions';
```

Create a new `count$` **Observable**.

Inside the constructor, connect `this.count$` **stream** to the **current** Store `count` **state**.

In the class' body, **define functions for each action**:

```js
increment() {
  this.store.dispatch(increment());
}

decrement() {
  this.store.dispatch(decrement());
}

reset() {
  this.store.dispatch(reset());
}
```

The next step is to generate a `div`, and a few **buttons** to **visualize the counter**.

Go to `src/app/counter/counter.component.html` and type:

```
<div>Current Count: {{ count$ | async }}</div>

<button (click)="increment()">Increment</button>

<button (click)="decrement()">Decrement</button>

<button (click)="reset()">Reset</button>
```

Here we create a **div-block** which displays the current count of our Counter Component.

We have three **buttons**:

- `increment` - increases the counter's value by one when a `click` event occurs
- `decrement` - decrements the counter by one when clicked
- `reset` - sets the counter's value to zero

[/slide]

[slide hideTitle]

# NgRx: Demo

11-NgRx-Demo

[/slide]