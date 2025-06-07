# React Multiple Choice Questions

<br/>

#### Q. If you want to import just the Component from the React library, what syntax do you use?

- [ ] `import React.Component from 'react'`
- [ ] `import [ Component ] from 'react'`
- [ ] `import Component from 'react'`
- [x] `import { Component } from 'react'`

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. If a function component should always render the same way given the same props, what is a simple performance optimization available for it?

- [x] Wrap it in the `React.memo` higher-order component.
- [ ] Implement the `useReducer` Hook.
- [ ] Implement the `useMemo` Hook.
- [ ] Implement the `shouldComponentUpdate` lifecycle method.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. How do you fix the syntax error that results from running this code?

```javascript
const person =(firstName, lastName) =>
{
  first: firstName,
  last: lastName
}
console.log(person("Jill", "Wilson"))
```

- [x] Wrap the object in parentheses.
- [ ] Call the function from another file.
- [ ] Add a return statement before the first curly brace.
- [ ] Replace the object with an array.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. If you see the following import in a file, what is being used for state management in the component?

`import React, {useState} from 'react';`

- [x] React Hooks
- [ ] stateful components
- [ ] math
- [ ] class components

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. Using object literal enhancement, you can put values back into an object. When you log person to the console, what is the output?

```javascript
const name = 'Rachel';
const age = 31;
const person = { name, age };
console.log(person);
```

- [ ] `{{name: "Rachel", age: 31}}`
- [x] `{name: "Rachel", age: 31}`
- [ ] `{person: "Rachel", person: 31}}`
- [ ] `{person: {name: "Rachel", age: 31}}`

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What is the testing library most often associated with React?

- [ ] Mocha
- [ ] Chai
- [ ] Sinon
- [x] Jest

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. To get the first item from the array ("cooking") using array destructuring, how do you adjust this line?

```javascript
const topics = ['cooking', 'art', 'history'];
```

- [ ] `const first = ["cooking", "art", "history"]`
- [ ] `const [] = ["cooking", "art", "history"]`
- [ ] `const [, first]["cooking", "art", "history"]`
- [x] `const [first] = ["cooking", "art", "history"]`

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. How do you handle passing through the component tree without having to pass props down manually at every level?

- [ ] React Send
- [ ] React Pinpoint
- [ ] React Router
- [x] React Context

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What should the console read when the following code is run?

```javascript
const [, , animal] = ['Horse', 'Mouse', 'Cat'];
console.log(animal);
```

- [ ] Horse
- [x] Cat
- [ ] Mouse
- [ ] undefined

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What is the name of the tool used to take JSX and turn it into createElement calls?

- [ ] JSX Editor
- [ ] ReactDOM
- [ ] Browser Buddy
- [x] Babel

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. Why might you use useReducer over useState in a React component?

- [ ] when you want to replace Redux
- [x] when you need to manage more complex state in an app
- [ ] when you want to improve performance
- [ ] when you want to break your production app

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. Which props from the props object is available to the component with the following syntax?

```javascript
<Message {...props} />
```

- [ ] any that have not changed
- [x] all of them
- [ ] child props
- [ ] any that have changed

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. Consider the following code from React Router. What do you call :id in the path prop?

```javascript
<Route path="/:id" />
```

- [ ] This is a route modal
- [x] This is a route parameter
- [ ] This is a route splitter
- [ ] This is a route link

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. If you created a component called Dish and rendered it to the DOM, what type of element would be rendered?

```javascript
function Dish() {
  return <h1>Mac and Cheese</h1>;
}

ReactDOM.render(<Dish />, document.getElementById('root'));
```

- [ ] `div`
- [ ] section
- [ ] component
- [x] `h1`

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What does this React element look like given the following function? (Alternative: Given the following code, what does this React element look like?)

```javascript
React.createElement('h1', null, "What's happening?");
```

- [ ] `<h1 props={null}>What's happening?</h1>`
- [x] `<h1>What's happening?</h1>`
- [ ] `<h1 id="component">What's happening?</h1>`
- [ ] `<h1 id="element">What's happening?</h1>`

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What property do you need to add to the Suspense component in order to display a spinner or loading state?

```javascript
function MyComponent() {
  return (
    <Suspense>
      <div>
        <Message />
      </div>
    </Suspense>
  );
}
```

- [ ] lazy
- [ ] loading
- [x] fallback
- [ ] spinner

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What do you call the message wrapped in curly braces below?

```javascript
const message = 'Hi there';
const element = <p>{message}</p>;
```

- [ ] a JS function
- [ ] a JS element
- [x] a JS expression
- [ ] a JSX wrapper

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What can you use to handle code splitting?

- [ ] `React.memo`
- [ ] `React.split`
- [x] `React.lazy`
- [ ] `React.fallback`

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. When do you use `useLayoutEffect`?

- [ ] to optimize for all devices
- [ ] to complete the update
- [ ] to change the layout of the screen
- [x] when you need the browser to paint before the effect runs

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

**Explanation:**
`useLayoutEffect` gets executed _before_ the `useEffect` hook without much concern for DOM mutation. Even though the React hook `useLayoutEffect` is set after the `useEffect` Hook, it gets triggered first!

#### Q. What is the difference between the click behaviors of these two buttons (assuming that this.handleClick is bound correctly)?

```javascript
A. <button onClick={this.handleClick}>Click Me</button>
B. <button onClick={event => this.handleClick(event)}>Click Me</button>
```

- [ ] Button A will not have access to the event object on click of the button.
- [ ] Button B will not fire the handler this.handleClick successfully.
- [ ] Button A will not fire the handler this.handleClick successfully.
- [x] There is no difference.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. How do you destructure the properties that are sent to the Dish component?

```javascript
function Dish(props) {
  return (
    <h1>
      {props.name} {props.cookingTime}
    </h1>
  );
}
```

- [ ] `function Dish([name, cookingTime]) { return <h1>{name} {cookingTime}</h1>; }`
- [x] `function Dish({name, cookingTime}) { return <h1>{name} {cookingTime}</h1>; }`
- [ ] `function Dish(props) { return <h1>{name} {cookingTime}</h1>; }`
- [ ] `function Dish(...props) { return <h1>{name} {cookingTime}</h1>; }`

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. When might you use `React.PureComponent`?

- [ ] when you do not want your component to have props
- [ ] when you have sibling components that need to be compared
- [x] when you want a default implementation of `shouldComponentUpdate()`
- [ ] when you do not want your component to have state

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. Why is it important to avoid copying the values of props into a component's state where possible?

- [ ] because you should never mutate state
- [ ] because `getDerivedStateFromProps()` is an unsafe method to use
- [x] because you want to allow a component to update in response to changes in the props
- [ ] because you want to allow data to flow back up to the parent

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What is the children prop?

- [ ] a property that adds child components to state
- [x] a special property that JSX creates on components that contain both an opening tag and a closing tag, referencing it's contents.
- [ ] a property that lets you set an array as a property
- [ ] a property that lets you pass data to child elements

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. Which attribute is React's replacement for using innerHTML in the browser DOM?

- [ ] injectHTML
- [x] dangerouslySetInnerHTML
- [ ] weirdSetInnerHTML
- [ ] strangeHTML

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. Which of these terms commonly describe React applications?

- [x] declarative
- [ ] integrated
- [ ] closed
- [ ] imperative

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. When using webpack, why would you need to use a loader?

- [ ] to put together physical file folders
- [x] to preprocess files
- [ ] to load external data
- [ ] to load the website into everyone's phone

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. A representation of a user interface that is kept in memory and is synced with the "real" DOM is called what?

- [x] virtual DOM
- [ ] DOM
- [ ] virtual elements
- [ ] shadow DOM

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. You have written the following code but nothing is rendering. How do you fix this problem?

```javascript
const Heading = () => {
  <h1>Hello!</h1>;
};
```

- [ ] Add a render function.
- [x] Change the curly braces to parentheses or add a return statement before the `h1` tag.
- [ ] Move the `h1` to another component.
- [ ] Surround the `h1` in a `div`.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. To create a constant in JavaScript, which keyword do you use?

- [x] const
- [ ] let
- [ ] constant
- [ ] var

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What do you call a React component that catches JavaScript errors anywhere in the child component tree?

- [ ] error bosses
- [ ] error catchers
- [ ] error helpers
- [x] error boundaries

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. In which lifecycle method do you make requests for data in a class component?

- [ ] constructor
- [x] componentDidMount
- [ ] componentWillReceiveProps
- [ ] componentWillMount

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. React components are composed to create a user interface. How are components composed?

- [ ] by putting them in the same file
- [x] by nesting components
- [ ] with webpack
- [ ] with code splitting

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. All React components must act like **\_** with respect to their props.

- [ ] monads
- [x] pure functions
- [ ] recursive functions
- [ ] higher-order functions

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What is `[e.target.id]` called in this code snippet?

```javascript
const handleChange = (e) => {
  setState((prevState) => ({ ...prevState, [e.target.id]: e.target.value }));
};
```

- [ ] a computed property name
- [ ] a set value
- [x] a dynamic key
- [ ] a JSX code string

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What is the name of this component?

```javascript
class Clock extends React.Component {
  render() {
    return <h1>Look at the time: {time}</h1>;
  }
}
```

- [x] Clock
- [ ] It does not have a name prop.
- [ ] React.Component
- [ ] Component

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. What is sent to an `Array.map()` function?

- [x] a callback function that is called once for each element in the array
- [ ] the name of another array to iterate over
- [ ] the number of times you want to call the function
- [ ] a string describing what the function should do

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. Why is it a good idea to pass a function to `setState` instead of an object?

- [ ] It provides better encapsulation.
- [ ] It makes sure that the object is not mutated.
- [ ] It automatically updates a component.
- [x] `setState` is asynchronous and might result in out of sync values.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

**Explanation:** Because `this.props` and `this.state` may be updated asynchronously, you should not rely on their values for calculating the next state.

#### Q. What package contains the render() function that renders a React element tree to the DOM?

- [ ] `React`
- [x] `ReactDOM`
- [ ] `Render`
- [ ] `DOM`

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

#### Q. How do you set a default value for an uncontrolled form field?

- [ ] Use the `value` property.
- [x] Use the `defaultValue` property.
- [ ] Use the `default` property.
- [ ] It assigns one automatically.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>
