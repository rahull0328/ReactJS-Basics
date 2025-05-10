# React Best Practices

## Use JSX ShortHand

Try to use JSX shorthand for passing boolean variables. Let\'s say you want to control the title visibility of a Navbar component.

**Bad:**

```jsx
return (
  <Navbar showTitle={true} />
);
```

**Good:**

```jsx
return(
  <Navbar showTitle />  
)
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Use Ternary Operators

Let\'s say you want to show a particular user\'s details based on role.

**Bad:**

```jsx
const { role } = user;

if(role === ADMIN) {
  return <AdminUser />
}else{
  return <NormalUser />
} 
```

**Good:**

```jsx
const { role } = user;

return role === ADMIN ? <AdminUser /> : <NormalUser />
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Use Object Literals

Object literals can help make our code more readable. Let\'s say you want to show three types of users based on their role. You can\'t use ternary because the number of options is greater than two.

**Bad:**

```jsx
const {role} = user

switch(role){
  case ADMIN:
    return <AdminUser />
  case EMPLOYEE:
    return <EmployeeUser />
  case USER:
    return <NormalUser />
}
```

**Good:**

```jsx
const {role} = user

const components = {
  ADMIN: AdminUser,
  EMPLOYEE: EmployeeUser,
  USER: NormalUser
};

const Component = components[role];

return <Componenent />;
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Use Fragments

Always use Fragment over Div. It keeps the code clean and is also beneficial for performance because one less node is created in the virtual DOM.

**Bad:**

```jsx
return (
  <div>
     <Component1 />
     <Component2 />
     <Component3 />
  </div>  
)
```

**Good:**

```jsx
return (
  <>
     <Component1 />
     <Component2 />
     <Component3 />
  </>  
)
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Do not define a function inside Render

Don\'t define a function inside render. Try to keep the logic inside render to an absolute minimum.

**Bad:**

```jsx
return (
    <button onClick={() => dispatch(ACTION_TO_SEND_DATA)}>    // NOTICE HERE
      This is a bad example 
    </button>  
)
```

**Good:**

```jsx
const submitData = () => dispatch(ACTION_TO_SEND_DATA)

return (
  <button onClick={submitData}>  
    This is a good example 
  </button>  
)
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Use Memo

React.PureComponent and Memo can significantly improve the performance of your application. They help us to avoid unnecessary rendering.

**Bad:**

```jsx
import React, { useState } from "react";

export const TestMemo = () => {
  const [userName, setUserName] = useState("faisal");
  const [count, setCount] = useState(0);
  
  const increment = () => setCount((count) => count + 1);
  
  return (
    <>
      <ChildrenComponent userName={userName} />
      <button onClick={increment}> Increment </button>
    </>
  );
};

const ChildrenComponent =({ userName }) => {
  console.log("rendered", userName);
  return <div> {userName} </div>;
};
```

Although the child component should render only once because the value of count has nothing to do with the ChildComponent. But, it renders each time you click on the button.
Output

Let\'s edit the ChildrenComponent to this:

**Good:**

```jsx
import React ,{useState} from "react";

const ChildrenComponent = React.memo(({userName}) => {
    console.log('rendered')
    return <div> {userName}</div>
})
```

Now no matter how many times you click on the button, it will render only when necessary.

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>

## Put CSS in JavaScript

Try to avoid raw JavaScript when you are writing React applications because organizing CSS is far harder than organizing JS.

**Bad:**

```jsx
// CSS FILE

.body {
  height: 10px;
}

//JSX

return <div className='body'>
   
</div>
```

**Good:**

```jsx
const bodyStyle = {
  height: "10px"
}

return <div style={bodyStyle}>

</div>
```

<div align="right">
    <b><a href="#">↥ back to top</a></b>
</div>