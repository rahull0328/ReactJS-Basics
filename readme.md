# ReactJS - Basics

> *Click &#9733; if you like the project. Your contributions are heartily ♡ welcome.*

<br/>

## Related Topics

* *[HTML Basics](https://github.com/learning-zone/html-basics)*
* *[CSS Basics](https://github.com/learning-zone/css-basics)*
* *[JavaScript Basics](https://github.com/learning-zone/javascript-basics)*
* *[React Coding Practice](react-coding-practice.md)*
* *[React Quick Reference](react-quick-reference.md)*
* *[Redux Quick Reference](redux-quick-reference.md)*
* *[Jest Quick Reference](jest-quick-reference.md)*
* *[React Best Practices](best-practices.md)*
* *[React Unit Testing](https://github.com/learning-zone/react-unit-testing)*
* *[React Project - ToDo App](https://github.com/learning-zone/react-todo-app)*
* *[React Project - My Store App](https://github.com/learning-zone/my-store-app)*

<br/>

## Table of Contents

* React
  * [Introduction](#-1-introduction)
  * [React Setup](#-2-react-setup)
  * [React JSX](#-3-react-jsx)
  * [React Components](#-4-react-components)
    * [Functional Components](#-41-functional-components)
    * [Class Components](#-42-class-components)
      * [React Lifecycle](#-421-react-lifecycle)
    * [Pure Components](#-43-pure-components)
    * [Higher Order Components](#-44-higher-order-components)
    * [Lazy Loading](#-45-lazy-loading)
  * [React Props](#-5-react-props)
  * [React State](#-6-react-state)
  * [React Events](#-7-react-events)
  * [React Lists](#-8-react-lists)
  * [React RESTful API](#-9-react-restful-api)
  * [React Forms](#-10-react-forms)
  * [React Hooks](#-11-react-hooks)
  * [React Context](#-12-react-context)
  * [React Router](#-13-react-router)
  * [React Error Boundaries](#-14-react-error-boundaries)
  * [React Refs](#-15-react-refs)
  * [React Composition](#-16-react-composition)
  * [React CSS Styling](#-17-react-css-styling)
  * [React Internationalization](#-18-react-internationalization)
  * [React Testing](#-19-react-testing)
  * [React Miscellaneous](#-20-react-miscellaneous)

* Redux
  * [Redux Overview](#-1-redux-overview)
  * [Redux Setup](#-2-redux-setup)
  * [Redux Data Flow](#-3-redux-data-flow)
  * [Redux Store](#-4-redux-store)
  * [Redux Actions](#-5-redux-actions)
  * [Redux Reducers](#-6-redux-reducers)
  * [Redux Middleware](#-7-redux-middleware)
  * [Redux Forms](#-8-redux-forms)
  * [Redux Miscellaneous](#-9-redux-miscellaneous)

<br/>

## # 1. INTRODUCTION

<br/>

## Q. What is React.js?

React is a JavaScript library created for building fast and interactive user interfaces for web and mobile applications. It is an open-source, component-based, front-end library responsible only for the application view layer.

The main objective of ReactJS is to develop User Interfaces (UI) that improves the speed of the apps. It uses virtual DOM (JavaScript object), which improves the performance of the app. The JavaScript virtual DOM is faster than the regular DOM. We can use ReactJS on the client and server-side as well as with other frameworks. It uses component and data patterns that improve readability and helps to maintain larger apps.

**Reference:**

* *[https://reactjs.org/tutorial/tutorial.html](https://reactjs.org/tutorial/tutorial.html)*

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How React works?

React implements a virtual DOM that is basically a DOM tree representation in Javascript. So when it needs to read or write to the DOM, it will use the virtual representation of it. Then the virtual DOM will try to find the most efficient way to update the browsers DOM.

Unlike browser DOM elements, React elements are plain objects and are cheap to create. React DOM takes care of updating the DOM to match the React elements. The reason for this is that JavaScript is very fast and it is worth keeping a DOM tree in it to speedup its manipulation.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. List some of the major advantages and limitations of React?

<p align="center">
  <img src="assets/react-features.png" alt="React-Features" width="500px" />
</p>

**Advantages:**  

* It relies on a virtual-dom to know what is really changing in UI and will re-render only what has really changed, hence better performance wise
* JSX makes components/blocks code readable. It displays how components are plugged or combined with.
* React data binding establishes conditions for creation dynamic applications.
* Prompt rendering. Using comprises methods to minimise number of DOM operations helps to optimise updating process and accelerate it.
Testable. React native tools are offered for testing, debugging code.
* SEO-friendly. React presents the first-load experience by server side rendering and connecting event-handlers on the side of the user:
    * React.renderComponentToString is called on the server.
    * React.renderComponent() is called on the client side.
    * React preserves markup rendered on the server side, attaches event handlers.  

**Limitations:**  

* Learning curve. Being not full-featured framework it is required in-depth knowledge for integration user interface free library into MVC framework.
* View-orientedness is one of the cons of ReactJS. It should be found 'Model' and 'Controller' to resolve 'View' problem.
* Not using isomorphic approach to exploit application leads to search engines indexing problems.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why does React emphasize on unidirectional data flow?

It is also known as one-way data flow, which means the data has one, and only one way to be transferred to other parts of the application. In essence, this means child components are not able to update the data that is coming from the parent component. In React, data coming from a parent is called **props**.

In React this means that:

* state is passed to the view and to child components
* actions are triggered by the view
* actions can update the state
* the state change is passed to the view and to child components

The view is a result of the application state. State can only change when actions happen. When actions happen, the state is updated. One-way data binding provides us with some key advantages

* Easier to debug, as we know what data is coming from where.
* Less prone to errors, as we have more control over our data.
* More efficient, as the library knows what the boundaries are of each part of the system.

In React, a state is always owned by one component. Any changes made by this state can only affect the components below it, i.e its `children`. Changing state on a component will never affect its parent or its siblings, only the children will be affected. This is the main reason that the state is often moved up in the component tree so that it can be shared between the components that need to access it.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to declare constant in react?

```js
// Constants.js

export const POSTURL = "http://localhost:3000/api/v1/patterns";
export const DELETEURL = "http://localhost:3000/api/v1/patterns/";

export const DeleteButton = require("./images/delete-icon.png");
export const LoadingWheel = require("./images/loading-wheel.gif");

```

```js
// App.js

import * as Constants from "./Constants";

const employee = {
  emp_id: 10,
  name: "Nakul Agate",
  email: "nakul.agate@email.com"
};

class App extends React.Component {
  render() {
    return (
      <div>
        <div>Employee Details :{JSON.stringify(employee)}</div>
        <div><img src={Constants.LoadingWheel} alt="Loading..." /></div>
      </div>
    );
  }
}
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-constants-knzec?file=/src/App.js)**

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is Destructuring?

Destructuring is a convenient way of accessing multiple properties stored in objects and arrays. It was introduced to JavaScript by ES6 and has provided developers with an increased amount of utility when accessing data properties in Objects or Arrays.

When used, destructuring does not modify an object or array but rather copies the desired items from those data structures into variables. These new variables can be accessed later on in a React component.

**Example:**

```js
/**
 * Destructuring in React
 */
import React from "react";

export default function App() {
  // Destructuring
  const [counter, setcounter] = React.useState(0);

  return (
    <>
      <button onClick={() => setcounter(counter + 1)}> Increment </button>
      <button onClick={() => setcounter(counter > 0 ? counter - 1 : 0)}>
        Decrement
      </button>

      <h2>Result: {counter}</h2>
    </>
  );
}
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/destructuring-in-react-6fxnbh?file=/src/App.js)**

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why is it necessary to start component names with a capital letter?

In JSX, lower-case tag names are considered to be HTML tags. However, lower-case tag names with a dot (property accessor) aren\'t.

When an element type starts with a lowercase letter, it refers to a built-in component like or and results in a string `<div>` or `<span>` passed to `React.createElement`. Types that start with a capital letter like compile to `React.createElement(Foo)` and correspond to a component defined or imported in your JavaScript file.

* `<component />` compiles to `React.createElement('component')` (html tag)
* `<Component />` compiles to `React.createElement(Component)`
* `<obj.component />` compiles to `React.createElement(obj.component)`

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are fragments?

Fragments allows to group a list of children without adding extra nodes to the DOM.

**Example:**

```js
class App extends React.Component {
  render() {
    return (
      <React.Fragment>
        <ChildA />
        <ChildB />
        <ChildC />
      </React.Fragment>
    )
  }
}
```

**Benefits:**

* It\'s a tiny bit faster and has less memory usage (no need to create an extra DOM node). This only has a real benefit on very large and/or deep trees, but application performance often suffers from death by a thousand cuts. This is one cut less.
* Some CSS mechanisms like Flexbox and CSS Grid have a special parent-child relationship, and adding divs in the middle makes it hard to keep the desired layout while extracting logical components.
* The DOM inspector is less cluttered.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is Virtual DOM?

In React, for every **DOM object**, there is a corresponding "virtual DOM object". A virtual DOM object is a representation of a DOM object, like a lightweight copy. A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing\'s power to directly change what\'s on the screen.

Manipulating DOM is slow, but manipulating Virtual DOM is fast as nothing gets drawn on the screen. So each time there is a change in the state of our application, virtual DOM gets updated first instead of the real DOM.

**&#9885; [Virtual DOM Example](https://codesandbox.io/s/react-virtual-dom-2w52y?file=/src/index.js)**

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the difference between ShadowDOM and VirtualDOM?

<p align="center">
  <img src="assets/shadow-dom.png" alt="DOM" width="600px" />
</p>

**1. Document Object Model:**

It a way of representing a structured document via objects. It is cross-platform and language-independent convention for representing and interacting with data in HTML, XML, and others. Web browsers handle the DOM implementation details, so we can interact with it using JavaScript and CSS.

**2. Virtual DOM:**

Virtual DOM is any kind of representation of a real DOM. Virtual DOM is about avoiding unnecessary changes to the DOM, which are expensive performance-wise, because changes to the DOM usually cause re-rendering of the page. It allows to collect several changes to be applied at once, so not every single change causes a re-render, but instead re-rendering only happens once after a set of changes was applied to the DOM.

**3. Shadow DOM:**

Shadow DOM is mostly about encapsulation of the implementation. A single custom element can implement more-or-less complex logic combined with more-or-less complex DOM. Shadow DOM refers to the ability of the browser to include a subtree of DOM elements into the rendering of a document, but not into the main document DOM tree.

**Difference:**

The virtual DOM creates an additional DOM. The shadow DOM simply hides implementation details and provides isolated scope for web components.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## # 2. REACT SETUP

<br/>

## Q. How to set up a react project with create react app?

Create React App is an officially supported way to create single-page React applications. It offers a modern build setup with no configuration. This tool is wrapping all of the required dependencies like **Webpack**, **Babel** for React project itself.

**Requirements:**

The Create React App is maintained by Facebook and can works on any platform, for example, macOS, Windows, Linux, etc. To create a React Project using create-react-app, you need to have installed the following things in your system.

* [Node version >= 14](https://nodejs.org/en/download/)
* [Visual Studio Code Editor](https://code.visualstudio.com/download)

**Installation:**

```js
npx create-react-app my-app
cd my-app
npm start
```

**Output:**

Running any of these commands will create a directory called **my-app** inside the current folder. Inside that directory, it will generate the initial project structure and install the transitive dependencies:

```js
my-app
├── README.md
├── node_modules
├── package.json
├── .gitignore
├── public
│   ├── favicon.ico
│   ├── index.html
│   ├── logo192.png
│   ├── logo512.png
│   ├── manifest.json
│   └── robots.txt
└── src
    ├── App.css
    ├── App.js
    ├── App.test.js
    ├── index.css
    ├── index.js
    ├── logo.svg
    ├── serviceWorker.js
    └── setupTests.js
```

**Reference:**

* *[https://create-react-app.dev/docs/getting-started/](https://create-react-app.dev/docs/getting-started/)*

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are the features of create react app?

**Create React App** is a command-line program that lets us create a new React project easily and build the project into artifacts that we can deploy. It is created by the React team and creates a scaffold to the app.

Below are the list of some of the features provided by create react app.

* React, JSX, ES6, Typescript and Flow syntax support.
* Autoprefixed CSS
* CSS Reset/Normalize
* Live-editing CSS and JS in local development server.
* A fast interactive unit test runner with built-in support for coverage reporting
* A build script to bundle JS, CSS, and images for production, with hashes and sourcemaps
* An offline-first service worker and a web app manifest, meeting all the Progressive Web App criteria.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What does eject do in create react app?

The `create-react-app` commands generate **React App** with an excellent configuration and helps you build your React app with the best practices in mind to optimize it. However, running the `eject` script will remove the single build dependency from your project. That means it will copy the configuration files and the transitive dependencies (e.g. `Webpack`, `Babel`, etc.) as dependencies in the `package.json` file. If you do that, you\'ll have to ensure that the dependencies are installed before building your project.

After running the `eject`, commands like `npm start` and `npm run build` will still work, but they will point to the copied scripts so you can tweak them. It won\'t be possible to run it again since all scripts will be available except the eject one.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to put React in production mode?

Create a simple `hello-world-app` using [create-react-app](https://create-react-app.dev/docs/getting-started).

```js
npx create-react-app hello-world-app
```

Modify the `App.js` file as shown below.

```js
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <h1>Hello world app</h1>
      </header>
    </div>
  );
}

export default App;
```

Run the app local server by running the following command

```js
npm start
```

On the local server (http://localhost:3000) you can see a simple React app displaying a "hello world" message. The next step is to make this app production-ready for deployment. Inside the root directory run the following command:

```js
npm run build
```

This creates a build directory inside the root directory, which bundles your React app and minifies it into simple HTML, CSS, and JavaScript files. This build folder serves your app via a simple entry point, `index.html`, where your entire React app resides. Running your app via a remote server means running this `index.html` file on the server.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are the common folder structures for React?

React doesn\'t have opinions on how you put files into folders. That said there are a few common approaches popular in the ecosystem you may want to consider.

**1. Grouping by features or routes:**

One common way to structure projects is to locate CSS, JS, and tests together inside folders grouped by feature or route.

```js
common/
  Avatar.js
  Avatar.css
  APIUtils.js
  APIUtils.test.js
feed/
  index.js
  Feed.js
  Feed.css
  FeedStory.js
  FeedStory.test.js
  FeedAPI.js
profile/
  index.js
  Profile.js
  ProfileHeader.js
  ProfileHeader.css
  ProfileAPI.js
```

**2. Grouping by file type:**

Another popular way to structure projects is to group similar files together, for example:

```js
api/
  APIUtils.js
  APIUtils.test.js
  ProfileAPI.js
  UserAPI.js
components/
  Avatar.js
  Avatar.css
  Feed.js
  Feed.css
  FeedStory.js
  FeedStory.test.js
  Profile.js
  ProfileHeader.js
  ProfileHeader.css
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are the popular React-specific linter?

**1. ESLint:**

ESLint is a popular JavaScript linter. There are plugins available that analyse specific code styles. One of the most common for React is an npm package called `eslint-plugin-react`.

```js
npm install -g eslint-plugin-react
```

This will install the plugin we need, and in our ESLint config file, we just need a few extra lines.

```js
"extends": [
    "eslint:recommended",
    "plugin:react/recommended"
]
```

```js
"scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject",
    "lint": "eslint src/**/*.js src/**/*.jsx"
}
```

**2. eslint-plugin-jsx-a11y:**

It will help fix common issues with accessibility. As JSX offers slightly different syntax to regular HTML, issues with `alt` text and `tabindex`, for example, will not be picked up by regular plugins.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the browser support for react applications?

By default, **Create React App** generated project supports all modern browsers. Support for Internet Explorer 9, 10, and 11 requires polyfills. For a set of polyfills to support older browsers, use **react-app-polyfill**.

The `browserslist` configuration controls the outputted JavaScript so that the emitted code will be compatible with the browsers specified.

**Example:**

```js
// package.json

"browserslist": {
  "production": [
    ">0.2%",
    "not dead",
    "not op_mini all"
  ],
  "development": [
    "last 1 chrome version",
    "last 1 firefox version",
    "last 1 safari version"
  ]
}
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Explain the use of Webpack and Babel in React?

**1. Babel:**

Babel is a JS transpiler that converts new JS code into old ones. It is a very flexible tool in terms of transpiling. One can easily add presets such as `es2015`, `es2016`, `es2017`, or `env`; so that Babel compiles them to ES5. Babel allows us to have a clean, maintainable code using the latest JS specifications without needing to worry about browser support.

**2. Webpack:**

Webpack is a modular build tool that has two sets of functionality — Loaders and Plugins. Loaders transform the source code of a module. For example, style-loader adds CSS to DOM using style tags. sass-loader compiles SASS files to CSS. babel-loader transpiles JS code given the presets. Plugins are the core of Webpack. They can do things that loaders can\'t. For example, there is a plugin called UglifyJS that minifies and uglifies the output of webpack.

**3. create-react-app:**

[create-react-app](https://create-react-app.dev/docs/getting-started/), a popular tool that lets you set up a React app with just one command. You don\'t need to get your hands dirty with Webpack or Babel because everything is preconfigured and hidden away from you.

**Example:** Quick Start

```bash
npx create-react-app my-app
cd my-app
npm start
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the difference between ReactDOM and React?

The ReactDOM module exposes DOM-specific methods, while React has the core tools intended to be shared by React on different platforms (e.g. React Native).

**React** package contains: `React.createElement()`, `React.createClass()`, `React.Component()`, `React.PropTypes()`, `React.Children()`

**ReactDOM** package contains: `ReactDOM.render()`, `ReactDOM.unmountComponentAtNode()`, `ReactDOM.findDOMNode()`, and react-dom/server that including: `ReactDOMServer.renderToString()` and `ReactDOMServer.renderToStaticMarkup()`.

**Example:**

```js
/**
 * React vs ReactDOM
 */
import { createRoot } from "react-dom/client";

export default function App() {
  return <h1>Hello React</h1>;
}

const rootElement = document.getElementById("root");
const root = createRoot(rootElement);

root.render(<App />);
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-vs-reactdom-o52zfc?file=/src/index.js)**

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is ReactDOM?

ReactDOM is a package that provides DOM specific methods that can be used at the top level of a web app to enable an efficient way of managing DOM elements of the web page.

ReactDOM provides the developers with an API containing the following methods

* render()
* findDOMNode()
* unmountComponentAtNode()
* hydrate()
* createPortal()

**1. render():**

```js
ReactDOM.render(element, container, callback)
```

Render a React element into the DOM in the supplied container and return a reference to the component (or returns null for stateless components). If the React element was previously rendered into container, this will perform an update on it and only mutate the DOM as necessary to reflect the latest React element. If the optional callback is provided, it will be executed after the component is rendered or updated.

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/reactdom-render-cyddr?file=/src/index.js)**

**2. hydrate():**

```js
ReactDOM.hydrate(element, container, callback)
```

This method is equivalent to the `render()` method but is implemented while using server-side rendering. This function attempts to attach event listeners to the existing markup and returns a reference to the component or null if a stateless component was rendered.

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-hydrate-e2bw5?file=/src/index.js)**

**3. unmountComponentAtNode():**

```js
ReactDOM.unmountComponentAtNode(container)
```

This function is used to unmount or remove the React Component that was rendered to a particular container. It returns true if a component was unmounted and false if there was no component to unmount.

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-unmountcomponentatnode-yued6)**

**4. findDOMNode():**

```js
ReactDOM.findDOMNode(component)
```

If this component has been mounted into the DOM, this returns the corresponding native browser DOM element. This method is useful for reading values out of the DOM, such as form field values and performing DOM measurements.

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-finddomnode-ft936?file=/src/index.js)**

**5. createPortal():**

```js
ReactDOM.createPortal(child, container)
```

createPortal allow us to render a component into a DOM node that resides outside the current DOM hierarchy of the parent component.

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-portal-v2h6q?file=/src/index.js)**

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to build a progressive web app with react?

*ToDo*

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the difference between create-react-app and webpack?

*ToDo*

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the difference between grunt and webpack?

*ToDo*

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## # 3. REACT JSX

<br/>

## Q. What is JSX?

JSX ( **JavaScript Expression** ) allows us to write HTML elements in JavaScript and place them in the DOM without any `createElement()` or `appendChild()` methods. JSX converts HTML tags into react elements. React uses JSX for templating instead of regular JavaScript. It is not necessary to use it, however, following are some pros that come with it.

* It is faster because it performs optimization while compiling code to JavaScript.
* It is also type-safe and most of the errors can be caught during compilation.
* It makes it easier and faster to write templates.

When JSX compiled, they actually become regular JavaScript objects. For instance, the code below:

```js
const hello = <h1 className = "greet"> Hello World </h1>
```

will be compiled to

```js
const hello = React.createElement {
    type: "h1",
    props: {
      className: "greet",  
      children: "Hello World"
    }
}
```

**Example:**

```js
export default function App() {
  return (
    <div className="App">
      <h1>Hello World!</h1>
    </div>
  );
}
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-jsx-zjmxvb?file=/src/App.js)**

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How JSX prevents Injection Attacks?

React DOM escapes any values embedded in JSX before rendering them. Thus it ensures that you can never inject anything that\'s not explicitly written in your application. Everything is converted to a string before being rendered.

For example, you can embed user input as below,

```js
export default class JSXInjectionExample extends React.Component {

  constructor(props) {
    super(props);
    this.state = {
      userContent: `JSX prevents Injection Attacks Example 
          <script src="http://example.com/malicious-script.js></script>`
    };
  }

  render() {
    return (
      <div>User content: {this.state.userContent}</div>
    );
  }
}

// Output
User content: JSX prevents Injection Attacks Example 
<script src="http://example.com/malicious-script.js></script>
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-jsxinjection-ckmu8z?file=/src/App.js)**

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are the benefits of new JSX transform?

The React 17 release provides support for a new version of the JSX transform. There are three major benefits of new JSX transform,

* It enables you to use JSX without having to import React.
* The compiled output relatively improves the bundle size.
* The future improvements provides the flexibility to reduce the number of concepts to learn React.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Is it possible to use React without rendering HTML?

It is possible with latest version (>=16.2). Below are the possible options:

```js
render() {
  return false
}
```

```js
render() {
  return null
}
```

```js
render() {
  return []
}
```

```js
render() {
  return <React.Fragment></React.Fragment>
}
```

```js
render() {
  return <></>
}
```

Note that React can also run on the server side so, it will be possible to use it in such a way that it doesn\'t involve any DOM modifications (but maybe only the virtual DOM computation).

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to write comments in React and JSX?

Writing comments in React components can be done just like comment in regular JavaScript classes and functions.

**React comments:**

```js
function App() {

  // Single line Comment

  /*
  * multi
  * line
  * comment
  **/

  return (
    <h1>My Application</h1>
  );
}
```

**JSX comments:**

```js
export default function App() {
  return (
    <div>
      {/* A JSX comment */}
      <h1>My Application</h1>
    </div>
  );
}
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>