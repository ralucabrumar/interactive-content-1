# Routing Concepts

[slide hideTitle]

# What is Routing?

Angular-Modules-and-routing-8-9-What-is-Routing

**Routing** is navigation on the **client-side**. 

It is the main element of **Single Page Applications** (**SPA**).

This type of navigation downloads the entire app on the first load, and if the URL changes, it only updates the page without **reloading**.

There is also **server-side** navigation, which works differently than **client-side** navigation.

**Server-side** navigation reloads on every **change** in the URL.

In the following example you can see the **difference between** the two types:

## Server-Side

[image assetsSrc="Angular-Modules-And-Routing.png" /]

First, the user clicks on the **anchor** element, and the browser detects the event.

Then, the browser makes a **GET** request to the route in the `href` tag.

On the **server** side, the request is processed, and a response (in the form of HTML, JSON, images, etc.) is returned.

Finally, the browser loads a completely **new webpage**, discarding the previous one.

## Client-Side

[image assetsSrc="Angular-Introduction-2.gif" /]

Once again, the browser detects a click event, but a **client-side routing library** handles it.

It detects that the URL is in the form of a **path** (e.g. `'/users/jane.michaels`) and does **not** perform a GET request.

The library then modifies the current URL, using the [History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API), and changes the **state** of the given component.

A front-end framework like Angular **processes** state changes and **renders** the required **components**.

If new data is required, it **fetches** it in small chunks.

Instead of downloading a whole webpage, Angular will download **only** the new assets, and will **generate** the client-ready HTML **locally**.

[/slide]

[slide hideTitle]

# Single Page Applications

Angular-Modules-and-routing-10-Single-page-applications

Single-page applications work by **leveraging the power** of JavaScript and frameworks like Angular.

In SPAs, the browser **sends an initial request** and receives an almost empty HTML file.

What it contains, however, are **references to JavaScript** files - the main engine of a single-page app.

In traditional (multi-page) web applications, when the route is changed, the server responds with an entirely different webpage.

In a SPA, when the **location is changed**, the **router** will load the corresponding component, which is already stored on the client.

Also, on the opposite side, a **difference in the content will** be represented in the URL.

This type of routing has many benefits, including:

- The resources for the app are loaded **only once**

- The state is maintainable across all pages

- We can use **browser history**

- Тhe user interface has increased response time

However, there is a minor downside - SPAs are not **optimized for search engine discovery**.

This means that our **application may rank lower** in search results or appear on wrong queries.

This can become **less of an issue** if we apply the appropriate metatags and use SEO (Search Engine Optimisation) friendly URLs.

[/slide]