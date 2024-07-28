# React Interview Questions and Answers

## 1. What is React?

**Answer:** React is an open-source JavaScript library for building user interfaces, especially single-page applications, developed by Facebook. It allows developers to create large web applications that can update and render efficiently in response to data changes.

## 2. What are the main features of React?

**Answer:** The main features of React include:

- **JSX:** A syntax extension for JavaScript that allows writing HTML directly within React.
- **Components:** Reusable pieces of UI that encapsulate their structure, functionality, and style.
- **Virtual DOM:** A lightweight copy of the actual DOM that React uses to optimize updates.
- **Unidirectional Data Flow:** Ensures that data flows in one direction, making it easier to debug and understand.
- **Lifecycle Methods:** Methods that allow developers to hook into different stages of a component's lifecycle.

## 3. What is JSX?

**Answer:** JSX stands for JavaScript XML. It is a syntax extension for JavaScript that allows writing HTML directly within React. It makes the code easier to read and write. JSX is then compiled into React.createElement() calls by Babel.

## 4. What is the Virtual DOM, and how does it work?

**Answer:** The Virtual DOM is a programming concept where a virtual representation of the UI is kept in memory and synced with the real DOM. This process is known as reconciliation. React uses the Virtual DOM to optimize DOM manipulation by batching updates and minimizing direct DOM interactions, leading to improved performance.

## 5. What are props in React?

**Answer:** Props (short for properties) are read-only attributes used to pass data from parent components to child components. Props help make components reusable by giving them the ability to receive dynamic data.

## 6. What is state in React?

**Answer:** State is an object that holds information that may change over the lifetime of the component. Unlike props, state is managed within the component (usually initialized in the constructor or via the `useState` hook in functional components) and can change in response to user actions or other events.

## 7. What are lifecycle methods in React?

**Answer:** Lifecycle methods are special methods in React components that are called at different stages of the component's lifecycle. Some common lifecycle methods include:

- `componentDidMount`: Called after the component is rendered for the first time.
- `componentDidUpdate`: Called after the component is updated.
- `componentWillUnmount`: Called just before the component is unmounted and destroyed.
- `shouldComponentUpdate`: Determines if a component should re-render.

## 8. What are hooks in React?

**Answer:** Hooks are functions that let you use state and other React features in functional components. Some commonly used hooks include:

- `useState`: Allows you to add state to a functional component.
- `useEffect`: Lets you perform side effects in functional components (e.g., data fetching, subscriptions).
- `useContext`: Lets you subscribe to React context without nesting.

## 9. What is the difference between a controlled and uncontrolled component?

**Answer:**

- **Controlled Component:** A component whose form data is handled by the state within the component. The component renders form elements and controls their behavior via event handlers.
- **Uncontrolled Component:** A component that maintains its own internal state. Form data is handled by the DOM itself, with React refs used to access form values.

## 10. How do you handle forms in React?

**Answer:** Forms in React can be handled using controlled components, where form elements are controlled via state and event handlers. This allows React to control form inputs and manage the form data. For example:

```javascript
class MyForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = { value: "" };
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({ value: event.target.value });
  }

  handleSubmit(event) {
    alert("A name was submitted: " + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input
            type="text"
            value={this.state.value}
            onChange={this.handleChange}
          />
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```

## 11. What is Redux, and how does it relate to React?

**Answer:** Redux is a predictable state container for JavaScript applications, often used with React for managing application state. It follows three principles:

- **Single Source of Truth:** The state of the entire application is stored in a single object.
- **State is Read-Only:** The only way to change the state is to dispatch an action.
- **Changes are Made with Pure Functions**: Reducers are pure functions that take the current state and an action as arguments and return a new state.

## 12. What is the Context API in React?

**Answer:** The Context API is a feature in React that allows for global state management. It enables components to share values like user authentication, themes, or settings without passing props through every level of the component tree. It is a lighter alternative to Redux for simple state management needs.

## 13. What is the difference between React and React Native?

**Answer:** React is a JavaScript library for building user interfaces for web applications, while React Native is a framework for building native mobile applications using React. React Native uses native components instead of web components for building mobile interfaces.

## 14. How do you optimize performance in a React application?

**Answer:** Performance in a React application can be optimized by:

- Using the Production build of React.
- Implementing code-splitting and lazy loading using `React.lazy` and `Suspense`.
- Using `shouldComponentUpdate` or `React.memo` to prevent unnecessary re-renders.
- Using the Virtual DOM efficiently.
- Avoiding inline functions and object creation in render methods.
- Using immutable data structures to simplify state updates.

## 15. What are higher-order components (HOCs) in React?

**Answer:** Higher-Order Components (HOCs) are functions that take a component and return a new component with additional props or behaviors. They are used for code reuse, logic abstraction, and enhancing components. An example HOC might be one that provides authentication logic to a component:

```javascript
const withAuth = (WrappedComponent) => {
  return class extends React.Component {
    render() {
      const { isAuthenticated } = this.props;
      if (!isAuthenticated) {
        return <Redirect to="/login" />;
      }
      return <WrappedComponent {...this.props} />;
    }
  };
};
```

## 16. How does React handle events?

**Answer:** React handles events using a synthetic event system that wraps the native browser events to ensure consistent behavior across different browsers. Event handlers in React are written in camelCase and passed as props to elements, and the event object is passed as an argument to the event handler:

```javascript
class MyComponent extends React.Component {
  handleClick(event) {
    alert("Button clicked");
  }

  render() {
    return <button onClick={this.handleClick}>Click Me</button>;
  }
}
```

## 17. What is React Router, and why would you use it?

**Answer:** React Router is a standard library for routing in React applications. It enables navigation between different components, changing the browser URL and keeping the UI in sync with the URL. React Router allows developers to create single-page applications with navigation capabilities, without refreshing the entire page.

## 18. What are fragments in React, and how are they used?

**Answer:** Fragments are a way to group multiple elements without adding extra nodes to the DOM. They are used when a component needs to return multiple elements, but you don't want to wrap them in an extra `div`. Fragments can be used with the shorthand syntax `<>` and `</>` or the `React.Fragment` element:

```javascript
return (
  <>
    <ChildA />
    <ChildB />
    <ChildC />
  </>
);
```

## 19. What is the purpose of keys in React?

**Answer:** Keys are used to identify elements in a list and help React determine which items have changed, are added, or are removed. Keys should be unique among siblings and are critical for optimizing the rendering process. Without keys, React may re-render the entire list on updates, leading to performance issues.

## 20. How do you manage state in a React application with multiple components?

**Answer:** State can be managed in a React application with multiple components using:

- **Lifting State Up:** Moving the state to the closest common ancestor component and passing it down as props.
- **Context API:** Using React's Context API for global state management.
- **State Management Libraries:** Utilizing libraries like Redux, MobX, or Recoil for more complex state management needs.
- **Hooks:** Using custom hooks to encapsulate and share stateful logic.
