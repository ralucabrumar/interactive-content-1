# Softuni Forum Workshop: Part 1

[slide hideTitle]

# Task Requirements

**Here is a link to the** [resources](https://videos.softuni.org/resources/javascript/javascript-angular/04-Components-Workshop.zip) **for this task.**

You will be provided with a skeleton (HTML and CSS). 

When starting the `index.html`, the following page will appear:

[image assetsSrc="Angular-Components-Workshop.png" /]

The application is a forum, where each registered user can create a theme or post a comment. 

For now, your task is to check the given skeleton (HTML and CSS files) and **split them into components**, so each part can be **reusable**.

Be careful when you structure the components.

[/slide]

[slide hideTitle]

# MongoDB

Before you start with creating a new project in Angular you need to install MongoDB. 

You can find an installation guide in the provided [document](https://mega.nz/file/bMZC3ThT#1F--LRBifNwhKe_qg2eUgE9ZpV0u2tSx6u2jjpZO3cY).

After the successful installation, your database will be empty, so you can load the provided from us initial data in it as follows:

- Download the provided folder named `forum`.

- You have to have mongod running on a separate system command line.

- Open a new command line and in the console write the following command:

`mongorestore -d forum C:\Users\Name\Desktop\forum`

**Note** `C:\Users\Name\Desktop\forum`- **replace with the path of the folder** `forum` **in your computer!!**

On the console you will see something like this:

[image assetsSrc="Angular-Components-Workshop(1).png" /]

**This is it!**

Now you can check if the **db** is in your **dbs** using the following commands:

[image assetsSrc="Angular-Components-Workshop(2).png" /]

[/slide]

[slide hideTitle]

# REST API

You are also provided with a [REST API](https://mega.nz/file/yN4k0RoS#pGmJUZli5wta8YIUC496T10bSv45sgbm62MeIX8vKmQ).

To bring life to that API you should first install the dependencies with the command `npm install`. 

After that, type the command `npm start`. 

To fetch the themes, you will have to make a GET request on `localhost:3000/api/themes`.

Here are the REST API endpoints specifications:

**Base Url:** `https://localhost:3000/api`

| **HTTP Method** | **Description** | **Endpoint** | **Expect** | **Login Required** |
|:---:|:---:|:---:|:---:|:---:|
| `POST`   | Signing up            | `/users/register`                 | `username`, `email`, `password`, `rePassword`, `tel` - optional     | No  |
| `POST`   | Signing in            | `/users/login`                  | `username`, `password`  | No  |
| `POST`   | Logging out           | `/users/logout`                  |             | Yes |
| `GET`    | Get all themes        | `/themes`                        |             | No  |
| `POST`   | Post new Theme        | `/themes`                        | `themeName`, `postText`   | Yes |
| `POST`   | Post comment in Theme  | `/themes/:themeId`                | `postText`    | Yes |
| `PUT`    | Subscribe to theme    | `/themes/:themeId`               |             | Yes |
| `GET`    | Get latest posts      | `/posts?limit=5`                 |             | No  |
| `PUT`    | Edit post (possible only for the creator of this post)             | `/themes/:themeId/posts/:postId`  | `postText`    | Yes |
| `DELETE` | Delete post (possible only for the creator of this post)            | `/themes/:themeId/posts/:postId` |             | Yes |
| `PUT`    | Like a post           |`/likes/:postId`                |             | Yes |
| `GET`    | Get user info / **Verify if user is logged in** | `/users/profile`                  |             | Yes |
| `PUT`    | Update user info      | `/users/profile`                 | `username`, `email`, `tel` - optional  | Yes |


## Logged/Unlogged User

**NOTE: Because we have not covered authentication yet (how to log in and register), you can hardcode it with a variable.**

**Logged out** users see the login and Register buttons/links.


[/slide]

[slide hideTitle]

# Implementation of the Main Section

After the backend is ready to use, you should **fetch all themes** and **list them** on the home page in the format you saw in the skeleton.

The **themes** **in the main** section should be **descending sorted by the subscribers**.

Each theme should have a **title**, **date** (when the theme is created), the username of the creator, **count of the subscribers** of the theme. 

[image assetsSrc="Angular-Components-Workshop(3).png" /]

[/slide]

[slide hideTitle]

# Implementation of the Aside Section

In the **Recent posts section, only the 5 latest posts** must be shown! 

`https://localhost:3000/api/posts?limit=5` 

The posts will be returned from the REST-API **sorted by the time of creation**.

Each component should have a **title (the title of the theme)**, a **username** of the user, to whom the last comment in the theme belongs, and the **time** the post was created.


[image assetsSrc="Angular-Components-Workshop(4).png" /]

[/slide]

