# REACTJS

### 1. What is React?

React is a popular JavaScript library created by Facebook for building user interfaces. It’s great for developing dynamic, fast, and efficient web applications, especially single-page apps.

### 2. What makes React special?

React stands out because of:

- **JSX:** Lets you write HTML-like syntax in JavaScript.
- **Components:** Reusable UI elements that keep code modular.
- **Virtual DOM:** Makes updates faster by minimizing direct changes to the actual DOM.
- **One-way Data Flow:** Keeps data flow predictable and easy to manage.
- **Lifecycle Methods:** Gives you control over a component’s behavior at different stages.

### 3. What is JSX?

JSX is a syntax extension that lets you write HTML inside JavaScript. It makes code more readable and expressive. Under the hood, JSX is converted into regular JavaScript using `React.createElement()`.

### 4. What is the Virtual DOM?

Instead of updating the actual DOM (which is slow), React first updates a virtual copy, figures out what changed, and then updates only those parts in the real DOM. This makes React super efficient.

### 5. What are props in React?

Props (short for “properties”) let you pass data from a parent component to a child component. They’re read-only, meaning they can’t be changed by the component receiving them.

### 6. What is state in React?

State is a component’s private data storage. Unlike props, state can be changed, making it useful for tracking things like user input or dynamic content updates.

### 7. What are lifecycle methods?

Lifecycle methods are functions that run at different stages of a component’s life. Some key ones:

- `componentDidMount`: Runs after the component first appears.
- `componentDidUpdate`: Runs when the component updates.
- `componentWillUnmount`: Runs just before the component is removed.

### 8. What are hooks in React?

Hooks let you use state and other React features in functional components. Some key hooks:

- `useState`: Adds state to a function component.
- `useEffect`: Runs code after renders (great for fetching data).
- `useContext`: Shares data across components without prop drilling.

### 9. What’s the difference between controlled and uncontrolled components?

- **Controlled Component:** The form inputs are controlled via React state.
- **Uncontrolled Component:** The form manages its own state, and React just accesses the values when needed.

### 10. How do you handle forms in React?

Forms in React use controlled components, where state tracks input values. Example:

```jsx
function MyForm() {
  const [value, setValue] = React.useState("");

  const handleSubmit = (event) => {
    event.preventDefault();
    alert(`Submitted: ${value}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input value={value} onChange={(e) => setValue(e.target.value)} />
      <button type="submit">Submit</button>
    </form>
  );
}
```

### 11. What is Redux?

Redux is a state management library that helps manage complex application state. It follows three core principles:

1. **Single Source of Truth:** All state is stored in one object.
2. **State is Read-Only:** You update it by dispatching actions.
3. **Changes are Made with Pure Functions:** Reducers handle state updates predictably.

### 12. What is the Context API?

Context API is React’s built-in way to manage global state, making it easier to share data across components without passing props manually at every level.

### 13. React vs. React Native—what’s the difference?

- **React:** Builds web applications.
- **React Native:** Builds mobile apps using native components instead of HTML.

### 14. How do you optimize React performance?

- Use **React’s production build**.
- Implement **lazy loading** with `React.lazy`.
- Use **`React.memo`** to prevent unnecessary re-renders.
- Minimize **inline functions** inside renders.

### 15. What are Higher-Order Components (HOCs)?

HOCs are functions that take a component and return a new one with extra features. Example: Adding authentication logic:

```jsx
const withAuth = (Component) => (props) =>
  props.isAuthenticated ? <Component {...props} /> : <Redirect to="/login" />;
```

### 16. How does React handle events?

React uses **synthetic events**, a wrapper around native events for better cross-browser compatibility. Example:

```jsx
<button onClick={() => alert("Clicked!")}>Click me</button>
```

### 17. What is React Router?

React Router manages navigation in React apps, enabling **single-page app behavior** where different components load based on the URL without refreshing the page.

### 18. What are fragments in React?

Fragments let you group multiple elements without adding extra DOM nodes. Example:

```jsx
<>
  <Header />
  <Content />
  <Footer />
</>
```

### 19. Why use keys in lists?

Keys help React track list items efficiently, preventing unnecessary re-renders. Always use a **unique ID** as a key when mapping over lists.

### 20. How do you manage state across multiple components?

- **Lifting State Up:** Move state to the nearest common parent.
- **Context API:** Manage global state.
- **State Management Libraries (Redux, MobX, Recoil):** For complex apps.

### 21. What’s the difference between class components and functional components in React?

**Class Components:**

- Defined using the ES6 `class` syntax.
- Can manage state and lifecycle methods.
- Uses a `render()` method to return JSX.

**Functional Components:**

- Defined using regular JavaScript functions.
- Originally stateless, but now can use hooks like `useState` and `useEffect`.
- Simpler and more concise—preferred in modern React development.

#### Quick Comparison:

| Functional Components                       | Class Components                               |
| ------------------------------------------- | ---------------------------------------------- |
| Just a function that returns JSX            | Requires a `class` extending `React.Component` |
| No `render()` method                        | Uses `render()` to return JSX                  |
| Runs top-to-bottom once and doesn’t persist | Lifecycle methods keep it "alive" for updates  |
| Uses hooks for state (`useState`)           | Uses `this.state` and `this.setState`          |

---

### 22. What is `useEffect`, and how does it work?

`useEffect` is a React hook that lets you run side effects (like fetching data or setting up event listeners) in functional components. It replaces lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.

Here’s a basic example:

```javascript
import { useEffect } from "react";

function ExampleComponent() {
  useEffect(() => {
    console.log("Component mounted!");

    return () => {
      console.log("Component unmounted!");
    };
  }, []);

  return <div>Example</div>;
}
```

---

### 23. What is `React.memo`, and why would you use it?

`React.memo` is a higher-order component that helps prevent unnecessary re-renders. It memorizes (caches) the component and only re-renders when its **props change**.

```javascript
const MyComponent = React.memo(({ value }) => {
  return <div>{value}</div>;
});
```

This is useful for performance optimization, especially when dealing with expensive calculations or large component trees.

---

### 24. What is `useRef`, and how do you use it?

`useRef` is a React hook that lets you persist values **without causing re-renders**. It’s often used to reference DOM elements directly.

Example: Focusing an input field on button click:

```javascript
import { useRef } from "react";

function ExampleComponent() {
  const inputRef = useRef(null);

  return (
    <div>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current.focus()}>Focus Input</button>
    </div>
  );
}
```

---

### 25. What is `useContext`, and why is it useful?

`useContext` lets you access values from React’s **Context API** without wrapping everything in `<Context.Consumer>`.

Example:

```javascript
import { useContext } from "react";
import { ThemeContext } from "./ThemeContext";

function ExampleComponent() {
  const theme = useContext(ThemeContext);

  return <div style={{ background: theme.background }}>Themed Component</div>;
}
```

This makes passing global data like themes, auth status, or settings much easier.

---

### 26. What is **code-splitting** in React?

Code-splitting lets you **load only the necessary JavaScript** for a given page instead of loading everything at once. React does this using `React.lazy` and `Suspense`.

```javascript
import React, { Suspense, lazy } from "react";

const LazyComponent = lazy(() => import("./LazyComponent"));

function App() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <LazyComponent />
    </Suspense>
  );
}
```

This helps improve performance, especially for large applications.

---

### 27. What is **PropTypes**, and why use it?

`PropTypes` is a library that helps check the types of props passed to a component, reducing potential bugs.

Example:

```javascript
import PropTypes from "prop-types";

function MyComponent({ name, age }) {
  return (
    <div>
      {name} is {age} years old.
    </div>
  );
}

MyComponent.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number.isRequired,
};
```

This ensures `name` must be a string and `age` a number, making debugging easier.

---

### 28. What are **React Portals**?

React Portals let you render a component **outside its parent’s DOM hierarchy**, which is useful for modals, popups, and tooltips.

Example:

```javascript
import ReactDOM from "react-dom";

function PortalComponent() {
  return ReactDOM.createPortal(
    <div className="modal">I'm a portal!</div>,
    document.getElementById("portal-root")
  );
}
```

Even though this component is rendered elsewhere in the DOM, React still keeps its event handlers and state intact.

---

### 29. What is `useReducer`, and when should you use it?

`useReducer` is a React hook for managing **complex state logic**. It works similarly to Redux but is built into React.

Example: A simple counter:

```javascript
import { useReducer } from "react";

const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    case "decrement":
      return { count: state.count - 1 };
    default:
      return state;
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      Count: {state.count}
      <button onClick={() => dispatch({ type: "increment" })}>+</button>
      <button onClick={() => dispatch({ type: "decrement" })}>-</button>
    </div>
  );
}
```

`useReducer` is great for handling complex state updates that involve multiple conditions.

---

### 30. What’s the difference between `useEffect` and `useLayoutEffect`?

- **`useEffect`** runs asynchronously **after the render**.
- **`useLayoutEffect`** runs **before the browser repaints**, making it useful for synchronously measuring DOM changes.

Example:

```javascript
import { useEffect, useLayoutEffect } from "react";

function ExampleComponent() {
  useEffect(() => {
    console.log("useEffect runs after render.");
  });

  useLayoutEffect(() => {
    console.log("useLayoutEffect runs before paint.");
  });

  return <div>Example</div>;
}
```

---

### 31. How do you handle **errors** in React?

React uses **error boundaries** to catch JavaScript errors in a component tree and display a fallback UI.

Example:

```javascript
import { useState, useEffect } from "react";

function ErrorBoundary({ children }) {
  const [hasError, setHasError] = useState(false);

  useEffect(() => {
    const errorHandler = (error, errorInfo) => {
      console.error("Caught error:", error, errorInfo);
      setHasError(true);
    };

    window.addEventListener("error", errorHandler);
    return () => window.removeEventListener("error", errorHandler);
  }, []);

  if (hasError) {
    return <h1>Something went wrong.</h1>;
  }

  return children;
}

export default ErrorBoundary;
```

---

### 32. What are **custom hooks** in React?

Custom hooks let you **extract and reuse logic** across multiple components.

Example: A hook for fetching data:

```javascript
import { useState, useEffect } from "react";

function useFetch(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch(url)
      .then((res) => res.json())
      .then((data) => {
        setData(data);
        setLoading(false);
      });
  }, [url]);

  return { data, loading };
}
```

Now you can use `useFetch("https://api.example.com")` anywhere in your app.

---

### 33. How can you optimize a React application's performance?

To improve performance in a React app, you can:

- **Use `React.memo`** to avoid unnecessary re-renders.
- **Use `useMemo` and `useCallback`** to optimize expensive calculations and functions.
- **Lazy load components** using `React.lazy` and `Suspense`.
- **Paginate or implement infinite scroll** instead of loading huge data lists at once.
- **Avoid inline functions and objects** inside JSX (they create new instances on every render).
- **Use production builds** of React to remove development warnings.
- **Split code dynamically** using `import()` to only load needed components.

---

### 34. What is the purpose of the `key` prop in React?

The `key` prop helps React identify which list items have changed, been added, or removed, making rendering more efficient.

✅ **Good Practice**

```javascript
const listItems = items.map((item) => <li key={item.id}>{item.name}</li>);
```

🚫 **Bad Practice** (Using index as key can cause issues with reordering)

```javascript
const listItems = items.map((item, index) => <li key={index}>{item.name}</li>);
```

---

### 35. How do you manage side effects in React?

In functional components, side effects (e.g., data fetching, subscriptions) are handled using the `useEffect` hook.

```javascript
useEffect(() => {
  console.log("This runs on mount and when dependencies change.");
  return () => console.log("Cleanup before unmounting");
}, []);
```

In class components, lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` are used instead.

---

### 36. How do you pass data between sibling components?

Since siblings don’t share a direct connection, data is **lifted up** to their **common parent**, which then passes it as props.

```javascript
function Parent() {
  const [sharedData, setSharedData] = useState("Hello");

  return (
    <div>
      <ChildA data={sharedData} setData={setSharedData} />
      <ChildB data={sharedData} />
    </div>
  );
}

function ChildA({ data, setData }) {
  return <button onClick={() => setData("Updated")}>{data}</button>;
}

function ChildB({ data }) {
  return <div>{data}</div>;
}
```

Alternatively, **Context API** or **state management tools** (Redux, Zustand, etc.) can be used for global state.

---

### 37. What is a **Pure Component** in React?

A **Pure Component** in React is a class component that only re-renders when its **state or props actually change**. This improves performance by preventing unnecessary renders.

Example:

```javascript
class PureComponentExample extends React.PureComponent {
  render() {
    return <div>{this.props.value}</div>;
  }
}
```

For functional components, `React.memo` achieves the same behavior:

```javascript
const MemoizedComponent = React.memo(({ value }) => <div>{value}</div>);
```

---

### 38. How do you handle **routing** in React?

React uses the `react-router-dom` library for client-side routing.

```javascript
import { BrowserRouter as Router, Route, Routes, Link } from "react-router-dom";

function App() {
  return (
    <Router>
      <nav>
        <Link to="/home">Home</Link>
        <Link to="/about">About</Link>
      </nav>
      <Routes>
        <Route path="/home" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </Router>
  );
}
```

This ensures navigation without full page reloads.

---

### 39. What is `useImperativeHandle`, and when is it used?

`useImperativeHandle` is a hook that allows you to **customize the instance value** exposed when using `ref`. This is useful when **a parent component needs to control a child component’s behavior**.

```javascript
import { useImperativeHandle, forwardRef, useRef } from "react";

const Child = forwardRef((props, ref) => {
  useImperativeHandle(ref, () => ({
    focus: () => {
      inputRef.current.focus();
    },
  }));

  const inputRef = useRef();

  return <input ref={inputRef} />;
});

function Parent() {
  const childRef = useRef();

  return (
    <div>
      <Child ref={childRef} />
      <button onClick={() => childRef.current.focus()}>
        Focus Child Input
      </button>
    </div>
  );
}
```

---

### 40. How does React handle **reconciliation**?

Reconciliation is how React **efficiently updates the DOM** when something changes. Instead of replacing everything, React:

1. **Compares the Virtual DOM** to detect changes.
2. **Updates only the changed elements** (instead of re-rendering everything).
3. Uses **"keys"** in lists to track elements efficiently.

Example:

```javascript
const newElement = <h1>Hello</h1>;
ReactDOM.render(newElement, document.getElementById("root"));
```

If `newElement` changes, React will **only update the necessary parts** of the real DOM.

---

# **REDUX**

### 1. What is Redux?

Redux is like a **central brain** for managing state in JavaScript apps. It helps keep everything **organized, predictable, and easy to debug**. While it’s most popular with React, you can use it with **any JavaScript framework**.

---

### 2. What are the core principles of Redux?

Redux is built on **three simple rules**:

1. **Single source of truth** → All your app's state is stored in **one central place** (the store).
2. **State is read-only** → You **can’t change state directly**—you have to dispatch an action.
3. **Changes happen with pure functions** → Reducers handle state updates in a **pure and predictable way**.

---

### 3. What is an action in Redux?

An **action** is just a plain JavaScript object that describes **what happened** in your app.

💡 Every action must have a **type** (like `"ADD_TODO"` or `"FETCH_USER_SUCCESS"`) and can also carry extra data (payload).

Example:

```javascript
const addTodo = {
  type: "ADD_TODO",
  payload: { text: "Learn Redux" },
};
```

---

### 4. What is a reducer?

A **reducer** is a function that **takes the current state and an action, then returns the new state**.

Think of it as a **state transformer**—whenever an action is dispatched, the reducer decides **how the state should change**.

Example:

```javascript
function todoReducer(state = [], action) {
  if (action.type === "ADD_TODO") {
    return [...state, action.payload];
  }
  return state;
}
```

---

### 5. What is the Redux store?

The **store** is the **heart of Redux**. It holds the entire app state and provides methods to:

- **Get the current state**
- **Dispatch actions**
- **Listen for state changes**

You create a store like this:

```javascript
import { createStore } from "redux";
const store = createStore(todoReducer);
```

---

### 6. What is middleware in Redux?

Middleware is like a **middleman** between dispatching an action and updating the store. It lets you:

✅ **Log actions** (e.g., debugging)  
✅ **Handle async operations** (e.g., API calls)  
✅ **Modify or cancel actions**

Example:

```javascript
import { applyMiddleware, createStore } from "redux";
import thunk from "redux-thunk";

const store = createStore(todoReducer, applyMiddleware(thunk));
```

---

### 7. How do you handle async actions in Redux?

Since Redux is **synchronous by default**, you need middleware like:

- **Redux Thunk** (simpler, uses functions to handle async logic)
- **Redux Saga** (more powerful, uses generators for complex async workflows)

Example with **Redux Thunk**:

```javascript
const fetchData = () => {
  return async (dispatch) => {
    const response = await fetch("/api/data");
    const data = await response.json();
    dispatch({ type: "FETCH_SUCCESS", payload: data });
  };
};
```

---

### 8. Redux vs. Context API – What’s the difference?

| Feature    | Redux 🛠️                      | Context API 🌎            |
| ---------- | ----------------------------- | ------------------------- |
| Purpose    | Global state management       | Prop drilling alternative |
| Complexity | More structured, needs setup  | Simpler, built into React |
| Best for   | Large apps with complex state | Small to medium apps      |

Use **Context API** for lightweight state sharing, and **Redux** when you need a **scalable, predictable state management solution**.

---

### 9. What are selectors in Redux?

A **selector** is a function that extracts specific data from the Redux store.

💡 Instead of accessing the full state, selectors **help optimize performance** by computing only what's needed.

Example:

```javascript
const getCompletedTodos = (state) =>
  state.todos.filter((todo) => todo.completed);
```

---

### 10. How do you handle errors in Redux?

Good error handling in Redux involves:

✅ **Dispatching error actions** when something goes wrong  
✅ **Storing error messages in state**  
✅ **Using middleware** to catch and log errors

Example:

```javascript
const errorReducer = (state = null, action) => {
  if (action.type === "ERROR_OCCURRED") {
    return action.payload;
  }
  return state;
};
```

---

### 11. What does `combineReducers` do?

`combineReducers` lets you **split your state into multiple reducers**, making it easier to manage.

Example:

```javascript
import { combineReducers } from "redux";

const rootReducer = combineReducers({
  todos: todoReducer,
  user: userReducer,
});
```

This allows Redux to manage **separate pieces of state independently**.

---

### 12. How do you connect Redux to a React component?

Redux connects to React using the `connect` function from `react-redux`.

```javascript
import { connect } from "react-redux";

const MyComponent = ({ todos }) => {
  return (
    <ul>
      {todos.map((todo) => (
        <li key={todo.id}>{todo.text}</li>
      ))}
    </ul>
  );
};

const mapStateToProps = (state) => ({
  todos: state.todos,
});

export default connect(mapStateToProps)(MyComponent);
```

Alternatively, with hooks:

```javascript
import { useSelector } from "react-redux";

const MyComponent = () => {
  const todos = useSelector((state) => state.todos);
  return (
    <ul>
      {todos.map((todo) => (
        <li key={todo.id}>{todo.text}</li>
      ))}
    </ul>
  );
};
```

---

# React Hooks Questions and Answers

### 1. What are React Hooks?

Hooks are **special functions** that let you **use state and other React features** in functional components—no need for classes! They were introduced in **React 16.8** to make components **simpler and more reusable**.

---

### 2. What is `useState`?

`useState` lets you **add state** to a functional component.

📌 It gives you **two things**:  
1️⃣ The **current state value**  
2️⃣ A **function to update the state**

Example:

```javascript
const [count, setCount] = useState(0);
```

Now `count` starts at **0**, and you can update it using `setCount()`.

---

### 3. What is `useEffect`?

`useEffect` lets you **run code when your component mounts, updates, or unmounts**—just like lifecycle methods in class components!

Example:

```javascript
useEffect(() => {
  console.log("Component mounted or updated!");

  return () => {
    console.log("Component unmounted!");
  };
}, [dependencies]);
```

👀 If you pass an **empty array (`[]`)**, the effect runs **only once** (on mount).

---

### 4. What are the **rules** of hooks?

Hooks have **two simple rules**:  
✅ **Only call hooks at the top level** (no loops, conditions, or nested functions).  
✅ **Only call hooks inside React function components or custom hooks** (not in regular JS functions).

---

### 5. What is `useContext`?

`useContext` lets you **access values from React’s Context API** without needing a **Context Consumer**.

Example:

```javascript
const value = useContext(MyContext);
```

This makes it easier to **share global data** like themes, authentication, and language settings.

---

### 6. What is `useReducer`?

`useReducer` is like `useState`, but **better for complex state logic** (e.g., multiple state updates at once).

Example:

```javascript
const [state, dispatch] = useReducer(reducer, initialState);
```

Perfect for **state-heavy apps** where updating state is more than just `setCount(count + 1)`.

---

### 7. What is `useMemo`?

`useMemo` **remembers** expensive calculations so they don’t run on every render.

Example:

```javascript
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

🚀 This improves **performance** by avoiding unnecessary recalculations.

---

### 8. What is `useCallback`?

`useCallback` **remembers functions** so they don’t get recreated every render—helpful when passing callbacks to child components.

Example:

```javascript
const memoizedCallback = useCallback(() => {
  doSomething(a, b);
}, [a, b]);
```

🧠 Saves memory and avoids unnecessary re-renders!

---

### 9. What is `useRef`?

`useRef` is like a **"persistent variable"** that **doesn’t cause re-renders**.

✅ It can be used to **store a value across renders**  
✅ Or **directly reference a DOM element**

Example:

```javascript
const myRef = useRef(null);
```

This is useful for **managing focus, animations, or storing previous values**.

---

### 10. What is a **custom hook**?

A **custom hook** is just a **function that starts with "use" and calls other hooks**.

📌 Custom hooks **let you reuse logic** without duplicating code.

Example:

```javascript
function useCustomHook() {
  const [value, setValue] = useState(0);
  return [value, setValue];
}
```

---

### 11. How do you create a custom hook for fetching data?

Here’s a simple custom hook to **fetch data from an API**:

```javascript
import { useState, useEffect } from "react";

function useFetch(url) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch(url);
        const result = await response.json();
        setData(result);
      } catch (err) {
        setError(err);
      } finally {
        setLoading(false);
      }
    };
    fetchData();
  }, [url]);

  return { data, loading, error };
}
```

Now you can **reuse this logic** anywhere by calling:

```javascript
const { data, loading, error } = useFetch("https://api.example.com");
```

---

### 12. How do you handle **side effects** in functional components?

You use **`useEffect`** for side effects like:

✅ **Fetching data**  
✅ **Subscribing to events**  
✅ **Updating the DOM manually**

Example:

```javascript
useEffect(() => {
  console.log("This runs on mount and updates");

  return () => {
    console.log("Cleanup function runs on unmount");
  };
}, [dependencies]);
```

This helps keep **your component clean and efficient**.

---
