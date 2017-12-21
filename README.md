[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# What is React?

React.js is an open-source JavaScript library used to build user interfaces for single page applications.  That makes React the "V" (view) in "MVC".  It allows you to build reusable UI components and create web applications that can change data without reloading the page.

## Prerequisites

-   JavaScript and ES6.
-   Conceptual knowledge of MVC and Single Page Applications.

## Objectives

By the end of this, developers should be able to:

- Install and set up a basic React environment.
- Build a basic React app using components and JSX.

## Preparation

1.  Fork and clone this repository.
 [FAQ](https://github.com/ga-wdi-boston/meta/wiki/ForkAndClone)

### React Features

## JSX
  React uses JSX, an object-oriented programming language that looks a lot like HTML.  It allows us to easily create HTML elements right in our .js files with almost the exact syntax we are used to when building HTML pages.  There are some slight differences though.  For instance, when building a JSX element we can not add a class to that element by typing `<p class='my-class'></p>` because `class` is a reserved keyword in JavaScript.  Instead we would use `<p className='my-class'></p>`. With JSX you also have to make sure all self closing tags include the `/` before the end of the tag.

  So although JSX looks very familiar, it works a little differently than the HTML elements we are used to.  Here's an example of how JSX is used in React:

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
  As you can see, the JSX code is written straight into our javascript file.  When this code is run, the React component `Header` will be compiled down to a single DOM element, in this case the `<header>` element.  A React component can not be compiled to more than one DOM element.  This means the following code would not work because the `<p>` tag is not contained within the `<header>` tag:

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

## Leading Topic Heading

Here is where the talk begins. If you have not already included framing above,
it's appropriate to put it here. Link to introductory articles or documentation.
Motivate the next section.

Demos, exercises, and labs are labelled as such, followed by a colon and a
description of the activity starting with an [imperative
verb](https://en.wikipedia.org/wiki/Imperative_mood).

## Demo: Write a Demo

Demos are demonstrations, and developers should give their full attention to
them. It's a great time for them to take notes about important concepts before
applying them in an exercise.

Demos correspond to the "I do" portion of scaffolding from consultant training.

## Code-Along: Write an Code-Along

During the code-along, developers should apply concepts covered in the previous
demo, led by the consultant.
This is their first chance to generalize concepts introduced. Exercises should
be very focused, and flow natural into a lab.

Exercises correspond to the "We do" portion of scaffolding from consultant
training.

## Lab: Write a Lab

During labs, developers get to demonstrate their understanding of concepts from
demos and applied knowledge from exercises. Labs are an opportunity for
developers to build confidence, and also serve as a diagnostic tool for
consultants to evaluate developer understanding.

Labs should be timed explicitly using a timer. When estimating the time it will
take to complete a lab, it is better to overestimate. During labs, consultants
should circle the room and interact with developers, noting patterns and
prompting with hints on how to complete the lab. If developers end early, a
consultant may stop the lab timer. If developers do not finish in time, a
consultant may give more time at her discretion based on current talk pace, the
current estimate for the talk, and the importance of completing the lab while
consultant support is available.

Labs correspond to the "You do" portion of scaffolding from consultant
training.

## Additional Resources

-   Any useful links should be included in the talk material where the link is
    first referenced.
-   Additional links for further study or exploration are appropriate in this
    section.
-   Links to important parts of documentation not covered during the talk, or
    tools tangentially used but not part of the focus of the talk, are also
    appropriate.

## [License](LICENSE)

1.  All content is licensed under a CC­BY­NC­SA 4.0 license.
1.  All software code is licensed under GNU GPLv3. For commercial use or
    alternative licensing, please contact legal@ga.co.
