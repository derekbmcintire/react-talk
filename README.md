[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# What is React?

React.js is an open-source JavaScript library used to build user interfaces for single page applications. That makes React the "V" (view) in "MVC". It allows you to build reusable UI components and create web applications that can change data without reloading the page.

## Prerequisites

-   JavaScript and ES6.
-   Conceptual knowledge of the DOM, MVC and Single Page Applications.

## Objectives

By the end of this, developers should be able to:

- Install and set up a basic React environment.
- Build a basic React app using components and JSX.

## Preparation

1.  Fork and clone this repository.
 [FAQ](https://github.com/ga-wdi-boston/meta/wiki/ForkAndClone)

## Is React a Framework or Library?

React is a front end library, not a framework. A library is really just a code base that you can import to your project, and use the functions that it includes however you would like. A framework has that same functionality, but also applies rules and structure to how you should use them.

Although React is just a library, it's still powerful and often times compared to frameworks like AngularJS, VueJS or EmberJS.

<img src="https://c1.staticflickr.com/5/4588/24341535597_b06666c571_o.png">
<img src="https://c1.staticflickr.com/5/4731/27444210789_5a69b02d6c_o.png">
<img src="https://c1.staticflickr.com/5/4725/39175278312_efff757b7d_b.jpg">

According to Hacker News hiring trends, React is currently the most popular software technology sought after by employers. Since 2014 it has become extremely popular and has a large community of supporters that claim React is useful for almost all web applications. There are of course opposing views and people who believe React is overhyped and overused.

React's popularity means there are many resources, tutorials and plenty of community support if you want to learn.

## React.js vs React Native

ReactJS is a JavaScript library, used for building user interfaces and web applications.

React Native is a mobile framework that compiles to native app components, allowing you to build native mobile applications (iOS, Android, and Windows) in JavaScript.

## The Virtual DOM

<img src='https://cdn-images-1.medium.com/max/800/1*CqdIWZy0NMPQhYx2rKzo9g.png'>

Part of why React is so popular is that it uses a virtual DOM. The virtual DOM is a local copy of the DOM that React creates and then compares against the DOM whenever a change is made. This allows React to re-render only those elements which have changed.

## Components/JSX

In React, everything is a component. These components are reusable and are the building blocks of our application. To make components, React uses JSX, a JavaScript pre-processer that looks a lot like HTML. It allows us to easily create HTML elements right in our .js files with almost the exact syntax we are used to when building HTML pages.

There are some slight differences though. For instance, when building a JSX element we can not add a class to that element by typing `<p class='my-class'></p>` because `class` is a reserved keyword in JavaScript.  Instead we would use `<p className='my-class'></p>`. With JSX you also have to make sure all self closing tags include the `/` before the end of the tag.

So although JSX looks very familiar, it works a little differently than the HTML elements we are used to. Here's an example of how JSX is used in React:

```js
class Header extends Component {
  render() {
    return (
        <header className="App-header">
          <h1 className="App-title">Welcome to My React App!</h1>
        </header>
    );
  }
}
```
As you can see, the JSX code is written straight into our javascript file.  When this code is run, the React component `Header` will be compiled down to a single DOM element, in this case the `<header>` element. A React component can not be compiled to more than one DOM element. This means the following code would not work because the `<p>` tag is not contained within the `<header>` tag:

```js
class Header extends Component {
  render() {
    return (
        <header className="App-header">
          <h1 className="App-title">Welcome to My React App!</h1>
        </header>
        <p className="so-cool">My App is so cool!</p>
    );
  }
}
```
So now we are mixing our JSX with our javascript in the same file, and it looks a lot like the old way of writing `<script>` tags and inline styles in our `index.html` file.  You might be thinking, "Isn't that bad? Isn't that breaking our separation of concerns?"

React users would probably disagree and argue that separating HTML, JavaScript and CSS isn't really separating concerns, it's separating technologies.  What React is doing is turning concerns into small components that do a specific thing and can be moved, reused, or manipulated together without having to sift through several files to find all of the connections.  This new organization of code is one of the biggest reasons people love React.

## Installation

Getting started with react is pretty simple. The best place to start is, of course, the React docs: https://reactjs.org/docs/installation.html#creating-a-new-application

- First, from your command line run `npm install -g create-react-app`. This installs the create-react-app bundle, which has bable (compiles your React components and JSX into JavaScript) and webpack built in.
- Then, run `create-react-app my-app` replacing "my-app" with whatever name you like. This does everything you need to start building a React app.
- cd into your new app directory and run `npm start`.
- your app is now running at `localhost:3000`!

## App Template Walk Through

Go to `src/index.js` and look at imports.  Notice that we need to use both `import React from 'react';` and `import ReactDOM from 'react-dom';`.

Look at the following piece of code at the bottom:

```
ReactDOM.render(<App />, document.getElementById('root'));
registerServiceWorker();
```

This is where our app is being rendered to the DOM.  ReactDOM has a method called .render which takes two arguments.  The first is the JSX element that we want to render, and the second is the DOM element we want to render that JSX element to.  By default, React uses an element called `root`.  Go to `public/index.html` and find the `root` element.  As you can see, it's just an empty `<div>`, but when the app runs, all of our React components will be rendered into this one `<div>` and displayed on the page.

Next, go to `App.js`.

This is the JSX component is what we are rendering in the `index.js` file and will contain the entirety of our app within the `<div>` with the className `"App"`.  It currently contains a React logo, and an `<h1` element  within a `header` element as well as a `<p>` element with a sentence.  Let's change some stuff around to learn how things work.

First, create a new file called `header.js`, then copy and paste from `App.js` and change the class name to `Header`, and then delete everything outside of the `<header` tag that's within the return statement.  Change the export at the bottom of the page, and remove the './App.css' import.  Your code should look like this:

```
import React, { Component } from 'react'
import logo from './logo.svg'

class Header extends Component {
  render() {
    return (

        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
    )
  }
}

export default Header
```

Now go back to `App.js` and import `Header` from `./header.js`

Go to the browser and refresh. Your app should look the same.

Let's go back to `header.js` and change something this time.  Lets use a JavaScript variable to chnage our app title.

inside the `render()` function, above the `return` statement, make a variable:
```
const title = 'This is my first React app!'
```

then, inside the `<h1>` element replace the text with
```
{title}
```
Go back to the browser and refresh the page.  What do you see?

## App Demo

Demo the sample App and show off some functionality.

## Additional Resources

-   https://reactjs.org/
- http://jlongster.com/Removing-User-Interface-Complexity,-or-Why-React-is-Awesome
-   https://camjackson.net/post/9-things-every-reactjs-beginner-should-know
-   https://edgecoders.com/so-you-want-to-learn-react-js-a78801d3cd4d
-   https://medium.com/@zackargyle/stop-using-react-for-everything-c8297ac1a644
-
## [License](LICENSE)

1.  All content is licensed under a CC­BY­NC­SA 4.0 license.
1.  All software code is licensed under GNU GPLv3. For commercial use or
    alternative licensing, please contact legal@ga.co.
