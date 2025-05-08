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
// MultiLevelDropdown.jsx
import React, { useState } from 'react';
import './MultiLevelDropdown.css'; // external CSS for styles

const menuData = [
  { label: "Menu 1" },
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

const MultiLevelDropdown = () => {
  const [openIndex, setOpenIndex] = useState(null);

  const toggleMenu = (index) => {
    setOpenIndex(openIndex === index ? null : index);
  };

  return (
    <div className="dropdown-container">
      <ul className="dropdown">
        {menuData.map((item, index) => (
          <li
            key={index}
            className="dropdown-item"
            onMouseEnter={() => toggleMenu(index)}
            onMouseLeave={() => toggleMenu(null)}
          >
            {item.label}
            {item.submenu && (
              <ul className={`submenu ${openIndex === index ? 'show' : ''}`}>
                {item.submenu.map((subItem, subIndex) => (
                  <li key={subIndex} className="submenu-item">
                    {subItem.label}
                  </li>
                ))}
              </ul>
            )}
          </li>
        ))}
      </ul>
    </div>
  );
};

export default MultiLevelDropdown;

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