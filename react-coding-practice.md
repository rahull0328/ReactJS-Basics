# React Coding Practice

## Q. Create a multilevel dropdown menu in React?

```js
Input:
[
  {
    label: "Menu 1",
  },
  {
    label: "Menu 2",
    submenu: [{ label: "Sub Menu 1" }, { label: "Sub Menu 2" }],
  },
  {
    label: "Menu 3",
    submenu: [
      { label: "Sub Menu 1" },
      { label: "Sub Menu 2" },
      { label: "Sub Menu 3" },
      { label: "Sub Menu 4" },
    ],
  },
  {
    label: "Menu 4",
    submenu: [{ label: "Sub Menu 1" }, { label: "Sub Menu 2" }],
  },
];
```

<details><summary><b>Answer</b></summary>

```js

```

</details>

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. Create a functional component that displays data from https://reqres.in/api/users?

<details><summary><b>Answer</b></summary>

```js
import React, { useEffect, useState } from "react";
import axios from "axios";

export default function App() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    axios.get("https://reqres.in/api/users?page=1").then((response) => {
      setUsers(response.data.data);
    });
  }, []);

  return (
    <div>
      <ul>
        {users.map((user) => (
          <li key={user.id}>
            {user.first_name} {user.last_name}
          </li>
        ))}
      </ul>
    </div>
  );
}
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-rest-api-hmcx8p?file=/src/App.js)**

</details>

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. Write a program to display searched keyword in React?

<details><summary><b>Answer</b></summary>

```js
function App() {
  const [search, setSearch] = useState("");

  return (
    <div className="App">
      <h2>Update Data from an input</h2>

      <div className="input-display">
        Seached Keyword: <b>{search}</b>
      </div>

      <div className="inputs">
        <input
          className="input"
          type="text"
          value={search}
          placeholder="Seach Here"
          onChange={(e) => setSearch(e.target.value)}
        />
      </div>
    </div>
  );
}
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-update-dom-vu4il?file=/src/index.js)**

</details>

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. Create a functional component to show an alert message based on user input?

<details><summary><b>Answer</b></summary>

```js
function App() {
  const [phrase, setPhrase] = useState("");

  if (phrase === "Hello React") {
    alert("You may pass!");
  }

  return (
    <div className="App">
      <h2>What's the secret phrase?</h2>

      <input
        type="text"
        value={phrase}
        onChange={(e) => setPhrase(e.target.value)}
        placeholder="Enter a secret"
      />

      <p>
        Hint: It's <strong>Hello React</strong>
      </p>
    </div>
  );
}
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-alert-based-on-input-hk2ip?file=/src/index.js)**

</details>

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. Create a functional component in react to add two numbers?

<details><summary><b>Answer</b></summary>

```js
function App() {
  const [number1, setNumber1] = useState();
  const [number2, setNumber2] = useState();
  const [total, setTotal] = useState(number1 + number2);

  function calculateTotal() {
    setTotal(number1 + number2);
  }

  return (
    <div className="App">
      <h1>Adding Two Numbers</h1>
      <div>
        <input
          type="number"
          value={number1}
          onChange={(e) => setNumber1(+e.target.value)}
        />
        <input
          type="number"
          value={number2}
          onChange={(e) => setNumber2(+e.target.value)}
        />
      </div>

      <button onClick={calculateTotal}>Add Them!</button>
      <h2>Total: {total}</h2>
    </div>
  );
}
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-calculator-8ud1d?file=/src/index.js)**

</details>

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. Create a simple counter in react?

<details><summary><b>Answer</b></summary>

```js
const App = () => {
  const [counter, setCounter] = useState(0);

  const handleClick = (type) => {
    type === "increment" ? setCounter(counter + 1) : setCounter(counter - 1);
  };

  return (
    <div>
      <h2>Counter: {counter}</h2>
      <div className="buttons">
        <button onClick={() => handleClick("increment")}>Increment</button>
        <button onClick={() => handleClick("decrement")}>Decrement</button>
      </div>
    </div>
  );
};
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-counter-bhp4q?file=/src/App.js)**

</details>

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. Write a program to pass values to child using context in React?

<details><summary><b>Answer</b></summary>

```js
// Counter.js

const { useState, useContext } = React;

const CountContext = React.createContext();

const Counter = () => {
  const { count, increase, decrease } = useContext(CountContext);
  return (
    <h2>
      <button onClick={decrease}>Decrement</button>
      <span className="count">{count}</span>
      <button onClick={increase}>Increment</button>
    </h2>
  );
};
```

```js
// App.js

const App = () => {
  const [count, setCount] = useState(0);

  const increase = () => {
    setCount(count + 1);
  };
  const decrease = () => {
    setCount(count - 1);
  };

  return (
    <div>
      <CountContext.Provider value={{ count, increase, decrease }}>
        <Counter />
      </CountContext.Provider>
    </div>
  );
};
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-context-api-v8syu?file=/src/index.js)**

</details>

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Q. Create a ToDo list app using React?

<details><summary><b>Answer</b></summary>

```js
class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      userInput: "",
      list: []
    };
  }

  // Set a user input value
  updateInput(value) {
    this.setState({
      userInput: value
    });
  }

  // Add item if user input in not empty
  addItem() {
    if (this.state.userInput !== "") {
      const userInput = {
        // Add a random id which is used to delete
        id: Math.random(),

        // Add a user value to list
        value: this.state.userInput
      };

      // Update list
      const list = [...this.state.list];
      list.push(userInput);

      // reset state
      this.setState({
        list,
        userInput: ""
      });
    }
  }

  // Function to delete item from list use id to delete
  deleteItem(key) {
    const list = [...this.state.list];

    // Filter values and leave value which we need to delete
    const updateList = list.filter((item) => item.id !== key);

    // Update list in state
    this.setState({
      list: updateList
    });
  }

  render() {
    return (
      <>
        <h1>TODO LIST</h1>
        <div>
          <input
            type="text"
            placeholder="add item . . . "
            value={this.state.userInput}
            onChange={(item) => this.updateInput(item.target.value)}
          />
          <input type="button" onClick={() => this.addItem()} value="ADD" />
        </div>
        <div>
          <ul>
            {/* map over and print items */}
            {this.state.list.map((item) => {
              return (
                <li key={item.id} onClick={() => this.deleteItem(item.id)}>
                  {item.value}
                </li>
              );
            })}
          </ul>
        </div>
      </>
    );
  }
}
```

**&#9885; [Try this example on CodeSandbox](https://codesandbox.io/s/react-todo-list-hw45y?file=/src/App.js)**

</details>

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>