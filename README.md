# Front-end Job Interview Questions

This file contains a number of front-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

**Note:** Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## Table of Contents

  1. [General Questions](#general-questions)
  1. [HTML Questions](#html-questions)
  1. [CSS Questions](#css-questions)
  1. [JS Questions](#js-questions)
  1. [Testing Questions](#testing-questions)
  1. [Performance Questions](#performance-questions)
  1. [Network Questions](#network-questions)
  1. [Coding Questions](#coding-questions)
  1. [Fun Questions](#fun-questions)

## Getting Involved

  1. [Contributors](#contributors)
  1. [How to Contribute](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/CONTRIBUTING.md)
  1. [License](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/LICENSE.md)

#### General Questions:

* What did you learn yesterday/this week?
* What excites or interests you about coding?
* What is a recent technical challenge you experienced and how did you solve it?
* What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?
* Talk about your preferred development environment.
* Which version control systems are you familiar with?
* Can you describe your workflow when you create a web page?
* If you have 5 different stylesheets, how would you best integrate them into the site?
* Can you describe the difference between progressive enhancement and graceful degradation?
* How would you optimize a website's assets/resources?
* How many resources will a browser download from a given domain at a time?
  * What are the exceptions?
* Name 3 ways to decrease page load (perceived or actual load time).
* If you jumped on a project and they used tabs and you used spaces, what would you do?
* Describe how you would create a simple slideshow page.
* If you could master one technology this year, what would it be?
* Explain the importance of standards and standards bodies.
* What is Flash of Unstyled Content? How do you avoid FOUC?
* Explain what ARIA and screenreaders are, and how to make a website accessible.
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
* What does CORS stand for and what issue does it address?

#### HTML Questions:

* What does a `doctype` do?
  Used as an instruction to the browser to inform about the html version of the document how it should be rendered
* What's the difference between full standards mode, almost standards mode and quirks mode?
  They are the three modes used by the layout engines in web browsers
  Full Standards Mode
    * The behavior described is the same as described by HTML and CSS specifications - most browsers use full standard mode
    * Can enforce browsers to use standards mode with a <!DOCTYPE html>
  Almost Standards Mode
    * The document is almost fully compliant with all the implemented standards with the exception of a few quirks
  Quirks Mode
    * Alerts the browser to render the page in a backwards compatibility mode  or in legacy pages which was written before these standards were fixed (IE5, Navigator 4)
* What's the difference between HTML and XHTML?
  HTML - HyperText Markup Language
  XHTML - EXtensible HyperText Markup Language
    * Almost identical to HTML
    * Stricter than HTML
    * It is HTML redesigned as XML
    * A markup language where documents must be marked up correctly since there are many pages that contain "bad" HTML
* Are there any problems with serving pages as `application/xhtml+xml`?
  IE < 8 will show a download dialog for the pages instead of rendering them properly
* How do you serve a page with content in multiple languages?
  Use lang (or xml:lang for XHMTL in tags)
    e.g. <html lang = "en">
    e.g. <html xmlns="http://www.w3.org/1999/xhml" lang="en" xml:lang="en">
    e.g. <div lang="es">Yo hablo espanol un poco</div>
* What kind of things must you be wary of when design or developing for multilingual sites?
  Properly localizing content for different audiences based on their location like <meta charset='UTF-8'> (a tag that specifies what charset in your website is written in) and difference in word length for each language
* What are `data-` attributes good for?
  Allows you to store extra information or data in the DOM - wrting a valid HTML with embedded private data
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
  Building blocks? As in block elements?
  e.g. <article>, <audio>, <video>, <header>, <footer>
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
  They are all storage on the client side 
  Cookie - small piece of key-value pair with expire time and is sent on every request 
  sessionStorage - stored in the browser and not sent with every request, changes are scopes only to the current window/page/tabs as well as future visits to the site on the same window
  localStorage - also stored in the browser and not sent with every request and will persist even if browser/tabs are closed, changes made are saved and available for all current and future visits to the site
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
  `<script>` tag will block rendering of the page and will not continue to load until the script finishes
  `<script async>` will run the script async so it does NOT block rendering but will run as soon as the script is available so when finishing download, it stops rendering and runs the script
  `<script defer>` will defer the script to run after the page is done parsing and before an onload event. So, when finishing rendering, it runs the script. 
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
  CSS - good idea to prevent a flash of unstyles content which gives the user something to look at while the rest of the page is being parsed. 
  JS - good idea since JS blocks rendering by default and the DOM and CSSOM construction can be also delayed and therefore, best to keep scripts at the bottom of the page
* What is progressive rendering?
  When a HTTP response is flushed multiple times, a browser doesn't wait until the whole content is loaded and renders each part earlier.
* Have you used different HTML templating languages before?
  Nope.

#### CSS Questions:

* What is the difference between classes and IDs in CSS?
  IDs (#) - unique, each element can only one ID
  Classes (.) - NOT unique, can use the same class on multiple elements, use multiple classes on the same element
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
  "resetting" - removes all the native styles provided by browsers, absolutely no decorations at all (e.g. h1-h6, p, strong, em tags end up identical in terms of looks),
    * have to add all the decoration yourself
  "normalizing" - makes the built-in browser styling consistent across browsers (e.g. h1-h6 will appear bold, larger, etc. in a consistent way across browsers)
    * you are then supposed to add only the difference of decoration 
* Describe Floats and how they work.
  Float is a CSS positioning property
  When you float an element, it becomes a block box then it can be shifted to the left or right on the current line.
  Floats have left, right, none properties
    * used to push elements to the left or right so other elements wrap around it
  Use clear when you don't want an element to wrap around another element, such as float
  Think of it as a rubber duck to an edge of the bath tub
  .clearfix hack uses a clever CSS pseudo selector (:after) to clear floats
* Describe z-index and how stacking context is formed.
  Specifies the stack order of an element - an element with a greater stack order is always in front of an element vs. those with lower stack order
  Only works on positioned elements (position: absolute, relative, fixed)
* Describe BFC(Block Formatting Context) and how it works.
  BFC - the visual CSS rendering of a webpage to determine from which positioning and clearing should be done. 
* What are the various clearing techniques and which is appropriate for what context?
  clear: left | right | both;
    * on sibling of floated element

  overflow: hidden;
    * use it on parent 
* Explain CSS sprites, and how you would implement them on a page or site.
  A way to reduce the number of HTTP requests made for image resources in your site.
  Combine your background images into a single image and use the CSS background-image and background-position properties to display desired image segment.
    e.g. background: url(...) x-axis y-axis
    e.g. background-image
    e.g. background-position
* What are your favourite image replacement techniques and which do you use when?
  CSS image replacement - a technique of replacing a text element (usually a header tag) with an image
  e.g. replacing a logo on a page from text to image
* How would you approach fixing browser-specific styling issues?
  Making separate style sheets for specific browsers 
  Using libraries such as Bootstrap that handles these issues for you
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you ever used a grid system, and if so, what do you prefer?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Are you familiar with styling SVG?
* How do you optimize your webpages for print?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Describe pseudo-elements and discuss what they are used for.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* List as many values for the display property that you can remember.
* What's the difference between inline and inline-block?
  Both CSS display element 
  inline - width and height are not respected as well as top/bottom margins & paddings (meaning there can be an overlap)
  inline-block - allows you to set a width and height on the element, top/bottom margins & paddings are respected
* What's the difference between a relative, fixed, absolute and statically positioned element?
  Static - default so element will flow into the page as it would normall would
  Relative - relative to itself, giving it a position attribute (top: 10px; then it will shift its position 10px down from where it would normally be)
  Fixed - relative to the browser itself
  Absolute - relative its containing block (i.e. the first parent that is not positioned static, if not found, then <html> tag), allows you to literally place any page element exactly where you want it
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* How is responsive design different from adaptive design?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?

#### JS Questions:

* Explain event delegation
  JS event listeners fire not only on a single DOM element but on all its descendants
* Explain how `this` works in JavaScript
  Refers to the value of the binding of the current execution context
  Also `this` always refers to an object - a single object
  All functions in JS have properties just as object have properties
  When a function executes, it gets the this property - a variabe with the value of the object that invokes the function when this is used
* Explain how prototypal inheritance works
  Everything in JS in an object
  Core idea: an object can point to another object and inherit all its properties
  Prototype - when each object has an internal link to another object
* What do you think of AMD vs CommonJS?
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  Pronounced as iffy
  Because the above example is a function declaration and does invoke immediately due to the parenthesis 
  * What needs to be changed to properly make it an IIFE?
    It needs to be an anonymous function because IIFE needs to be invooked immediately without invooking it a function name so rewriting
      (function() {}());
    Function expression in JS returns a value
* What's the difference between a variable that is: `null`, `undefined` or undeclared?
  null - an object that has no value or an empty value ("no value")
  undefined - the value of the variable is undefined, a type w/ exactly one value: undefined
  * How would you go about checking for any of these states?
    typeof null - "object"
    typeof undefined - "undefined"
* What is a closure, and how/why would you use one?
  An inner function that has access to the outer function's variables
  You can create it by adding a function inside another function
  Why? For private variables/functions
* What's a typical use case for anonymous functions?
  I would use it for IIFE (Immediately-Invoked Function Expression) so that it executes immediately afer it is created 
* How do you organize your code? (module pattern, classical inheritance?)
* What's the difference between host objects and native objects?
  Host - existing in the environment
  Native - existing in JS
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
  `function Person(){}` - function declaration 
    Declares a function statement but does not execute but does get registered into the global namespace
  `var person = Person()` - function expression 
    Since it returns a value (i.e. has been defined and contains value reference to a Person function)
  `var person = new Person()` - function constructor
    Adding the keyword new means we are instantiating a new object of the Person class constructor 
    A function declaration is a just a regular function unless it has been instantitated
* What's the difference between `.call` and `.apply`?
  Call - a method that calls a function with a given `this` value and arguments provided individually 
    e.g. function.call(thisArg, arg1, arg2, arg3 ...)
  Apply - method that calls a function with given this value and arguments provided as an array
    e.g. func.apply(thisArg, [argsArray])
* Explain `Function.prototype.bind`.
  Method that creates a new function that will have `this` set to the first parameter passed to bind
* When would you use `document.write()`?

* What's the difference between feature detection, feature inference, and using the UA string?
* Explain Ajax in as much detail as possible.
  AJAX - Asynchronous JavaScript and XML
  Allows application to send and retrieve data to/from a server async without refreshing the page
  Example - your new emails on Gmail appear and are marked as new even if you have not refreshed the page
* What are the advantages and disadvantages of using Ajax?
* Explain how JSONP works (and how it's not really Ajax).
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
* Explain "hoisting".
  Refers to JS's default behavior of moving declaration to the top before execution (think of the difference between var and let)
  This means a variable can be declared after it has been used and also can be used before it has been declared
  var - scoped to the current function
  let - scoped to the current block
* Describe event bubbling.
  When events on an element will "bubble up" and also fire on all parents
  For example, when a mouse is clicked on a button, the same event is also triggered on all of that element's ancestors.
  Basically, event bubbles up from the originating element to the top of the DOM Tree
* What's the difference between an "attribute" and a "property"?
* Why is extending built-in JavaScript objects not a good idea?
* Difference between document load event and document DOMContentLoaded event?
* What is the difference between `==` and `===`?
  Both comparison operators 
  `==` - non-strict, compares value, implicit type conversion is done
    e.g. "2" == 2; //true because "2" is converted and then compares
  `===` - strict, compares type and value
    e.g. "2" == 2; //false
* Explain the same-origin policy with regards to JavaScript.
  Under this policy, a web browser permits scripts contained in a first web page to access data in a second web page but only if both web pages have the same origin.
  If a script in the different origin should be accessed, we can consider using CORS (Cross-Origin Resource Sharing) since the same-origin policy can prevent legitimate interactions between a server and clients of a known and trusted origin.
    Purpose: allows JS to consume a REST API served from a different origin
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?
  Indicates the code should be executed in "strict mode" - to make it easier to write "secure" JS like not allowing undeclared variables and prevents "bad syntax" 
  Should be declared in the beginning of a script
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
  In any languages, global variables are generally bad because of possible name clashes, hard to identify where the code appeared from, etc.
  But particularly bad for JS becasue JS defaults all variables to the global scope unless they are explictly defined elsewhere 
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
  Single Page Apps - web apps that load a single HTML page and dynamically update that page as user intereacts with the app
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
  Promises 
  Pros
  Cons
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
* Explain the difference between synchronous and asynchronous functions.
* What is event loop?
  * What is the difference between call stack and task queue?
* Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`

#### Testing Questions:

* What are some advantages/disadvantages to testing your code?
* What tools would you use to test your code's functionality?
* What is the difference between a unit test and a functional/integration test?
* What is the purpose of a code style linting tool?

#### Performance Questions:

* What tools would you use to find a performance bug in your code?
* What are some ways you may improve your website's scrolling performance?
* Explain the difference between layout, painting and compositing.

#### Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
* What are HTTP methods? List all HTTP methods that you know, and explain them.
  4 Basic Methods:
    GET - read
    POST - create
    PUT - update/replace
    DELETE - delete

  GET vs POST:
    GET - safe actions, able to be changed, remains in the browser history, has length restriction, more responsive and is more suited for AJAX since it can send/retrieve from a server asynchronously
      * Less secure and can be seen by the user in the URL
    POST - unsafe actions/sensitive data and dealing with long request since there is no restriction on data length, two-step process (sends header first and data = more secure)
      * used to store data in the db or submit data via form

#### Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20'; //'1020'
```

*Question: How would you make this work?*
```javascript
add(2, 5); // 7 
add(2)(5); // 7
/*var add = function(x) {
    return function(y) { return x + y; };
}*/
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join(""); //"goh angasal a m'i"
// split - splits a string object into an array of string
```

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```

#### Fun Questions:

* What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Who inspires you in the front-end community?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your coffee?


#### Contributors:

This document started in 2009 as a collaboration of [@paul_irish](https://twitter.com/paul_irish) [@bentruyman](https://twitter.com/bentruyman) [@cowboy](https://twitter.com/cowboy) [@ajpiano](https://twitter.com/ajpiano)  [@SlexAxton](https://twitter.com/slexaxton) [@boazsender](https://twitter.com/boazsender) [@miketaylr](https://twitter.com/miketaylr) [@vladikoff](https://twitter.com/vladikoff) [@gf3](https://twitter.com/gf3) [@jon_neal](https://twitter.com/jon_neal) [@sambreed](https://twitter.com/sambreed) and [@iansym](https://twitter.com/iansym).

It has since received contributions from over [100 developers](https://github.com/h5bp/Front-end-Developer-Interview-Questions/graphs/contributors).
