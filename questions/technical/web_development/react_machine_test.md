# Task Instructions

- **Step 1: Try It Yourself**
  Before diving into the provided solution, take a moment to solve the task using your own logic and creativity. This is a great opportunity to challenge yourself and apply your problem-solving skills!

- **Step 2: Review the Solution**
  Once you’ve given it your best shot, feel free to check out the provided solution. This will help you see different approaches and understand the nuances of the problem better.

# React Problem 1: Creating a Todo List

## Problem Description

Create a simple Todo List application using React. The application should have the following functionalities:

1. Add a new todo item.
2. Display the list of todo items.
3. Mark a todo item as completed.
4. Remove a todo item.

## Requirements

- The application should use functional components and hooks (useState).
- Each todo item should have an id, a text, and a completed status.
- The list of todo items should be displayed with the option to mark them as completed or to delete them.

## Solution

**App Component:**
Create the main `App` component which will manage the state and render other components.

```javascript
import React, { useState } from "react";
import TodoForm from "./TodoForm";
import TodoList from "./TodoList";

const App = () => {
  const [todos, setTodos] = useState([]);

  const addTodo = (todo) => {
    setTodos([...todos, { id: Date.now(), text: todo, completed: false }]);
  };

  const toggleComplete = (id) => {
    setTodos(
      todos.map((todo) =>
        todo.id === id ? { ...todo, completed: !todo.completed } : todo
      )
    );
  };

  const removeTodo = (id) => {
    setTodos(todos.filter((todo) => todo.id !== id));
  };

  return (
    <div>
      <h1>Todo List</h1>
      <TodoForm addTodo={addTodo} />
      <TodoList
        todos={todos}
        toggleComplete={toggleComplete}
        removeTodo={removeTodo}
      />
    </div>
  );
};

export default App;
```

**TodoForm Component:**
Create a form component to add new todos.

```javascript
import React, { useState } from "react";

const TodoForm = ({ addTodo }) => {
  const [input, setInput] = useState("");

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!input) return;
    addTodo(input);
    setInput("");
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={input}
        onChange={(e) => setInput(e.target.value)}
        placeholder="Add a new todo"
      />
      <button type="submit">Add</button>
    </form>
  );
};

export default TodoForm;
```

**TodoList Component:**
Create a component to display the list of todos.

```javascript
import React from "react";

const TodoList = ({ todos, toggleComplete, removeTodo }) => {
  return (
    <ul>
      {todos.map((todo) => (
        <li
          key={todo.id}
          style={{ textDecoration: todo.completed ? "line-through" : "none" }}
        >
          {todo.text}
          <button onClick={() => toggleComplete(todo.id)}>Complete</button>
          <button onClick={() => removeTodo(todo.id)}>Delete</button>
        </li>
      ))}
    </ul>
  );
};

export default TodoList;
```

# React Problem 2: Creating a Counter App

## Problem Description

Create a simple Counter application using React. The application should have the following functionalities:

1. Display the current count.
2. Increment the count by 1 when the "Increment" button is clicked.
3. Decrement the count by 1 when the "Decrement" button is clicked.
4. Reset the count to 0 when the "Reset" button is clicked.

## Requirements

- The application should use functional components and hooks (`useState`).

## Solution

**Create the Counter Component:**
Create the main `Counter` component which will manage the state and render the buttons.

```javascript
import React, { useState } from "react";
import "./App.css";

const Counter = () => {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  const decrement = () => {
    setCount(count - 1);
  };

  const reset = () => {
    setCount(0);
  };

  return (
    <div className="counter">
      <h1>Counter</h1>
      <p>Current Count: {count}</p>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
      <button onClick={reset}>Reset</button>
    </div>
  );
};

export default Counter;
```

**Add Some Basic Styling:**
Add some basic CSS to style the counter application. Create a App.css file:

```css
.counter {
  text-align: center;
  margin-top: 50px;
}

button {
  margin: 5px;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}
```

**Update the Main App Component:**
Update the App.js file to include the Counter component.

```javascript
import React from "react";
import Counter from "./Counter";
import "./App.css";

function App() {
  return (
    <div className="App">
      <Counter />
    </div>
  );
}

export default App;
```

# React Problem 3: Creating a Weather App

## Problem Description

Create a simple Weather application using React that fetches and displays weather information for a specified city. The application should have the following functionalities:

1. Input field to enter a city name.
2. Button to fetch the weather information.
3. Display the city name, temperature, and weather description.
4. Handle loading states and errors gracefully.

## Requirements

- Use functional components and hooks (`useState`, `useEffect`).
- Use a free weather API (e.g., OpenWeatherMap) to fetch weather data.
- The application should handle loading and error states.

## Solution

**Get an API Key:**
Sign up for a free API key at [OpenWeatherMap](https://openweathermap.org/).

**Create the Weather Component:**
Create a `Weather` component that fetches and displays weather information.

```javascript
import React, { useState } from "react";
import "./Weather.css";

const Weather = () => {
  const [city, setCity] = useState("");
  const [weather, setWeather] = useState(null);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  const fetchWeather = async () => {
    setLoading(true);
    setError(null);
    try {
      const response = await fetch(`Weather-API-from-website`);
      if (!response.ok) {
        throw new Error("City not found");
      }
      const data = await response.json();
      setWeather(data);
    } catch (err) {
      setError(err.message);
    } finally {
      setLoading(false);
    }
  };

  return (
    <div className="weather">
      <h1>Weather App</h1>
      <input
        type="text"
        value={city}
        onChange={(e) => setCity(e.target.value)}
        placeholder="Enter city"
      />
      <button onClick={fetchWeather}>Get Weather</button>
      {loading && <p>Loading...</p>}
      {error && <p className="error">{error}</p>}
      {weather && (
        <div className="weather-info">
          <h2>{weather.name}</h2>
          <p>Temperature: {weather.main.temp}°C</p>
          <p>Weather: {weather.weather[0].description}</p>
        </div>
      )}
    </div>
  );
};

export default Weather;
```

**Add Some Basic Styling:**
Create a `Weather.css` file for basic styling.

```css
.weather {
  text-align: center;
  margin-top: 50px;
}

input {
  padding: 10px;
  font-size: 16px;
  margin-right: 10px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

.weather-info {
  margin-top: 20px;
}

.error {
  color: red;
}
```

**Update the Main App Component:**
Update the `App.js` file to include the Weather component.

# React Problem 4: Build a Simple Form with Validation

## Problem Description

Create a simple form using React that includes fields for a user's name, email, and a message. Implement basic validation for the form inputs. The form should meet the following requirements:

1. **Name Field**: Must be non-empty.
2. **Email Field**: Must be a valid email address.
3. **Message Field**: Must be non-empty.
4. **Display Errors**: Show validation error messages below each field.

## Requirements

- Use functional components and hooks (`useState`).
- Implement form validation.
- Display appropriate error messages.

## Solution

**Create the Form Component:**
Create a Form component that includes fields for `name`, `email`, and `message` with validation logic.

```javascript
import React, { useState } from "react";
import "./Form.css";

const Form = () => {
  const [name, setName] = useState("");
  const [email, setEmail] = useState("");
  const [message, setMessage] = useState("");
  const [errors, setErrors] = useState({ name: "", email: "", message: "" });

  const validate = () => {
    let isValid = true;
    const errors = { name: "", email: "", message: "" };

    if (!name) {
      errors.name = "Name is required";
      isValid = false;
    }

    const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!email || !emailPattern.test(email)) {
      errors.email = "Invalid email address";
      isValid = false;
    }

    if (!message) {
      errors.message = "Message is required";
      isValid = false;
    }

    setErrors(errors);
    return isValid;
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (validate()) {
      alert("Form submitted successfully");
    }
  };

  return (
    <form onSubmit={handleSubmit} className="form">
      <div>
        <label htmlFor="name">Name:</label>
        <input
          type="text"
          id="name"
          value={name}
          onChange={(e) => setName(e.target.value)}
        />
        {errors.name && <p className="error">{errors.name}</p>}
      </div>
      <div>
        <label htmlFor="email">Email:</label>
        <input
          type="email"
          id="email"
          value={email}
          onChange={(e) => setEmail(e.target.value)}
        />
        {errors.email && <p className="error">{errors.email}</p>}
      </div>
      <div>
        <label htmlFor="message">Message:</label>
        <textarea
          id="message"
          value={message}
          onChange={(e) => setMessage(e.target.value)}
        />
        {errors.message && <p className="error">{errors.message}</p>}
      </div>
      <button type="submit">Submit</button>
    </form>
  );
};

export default Form;
```

**Add Basic Styling:**
Create a Form.css file to add some basic styling.

```css
.form {
  max-width: 500px;
  margin: auto;
}

label {
  display: block;
  margin: 10px 0 5px;
}

input,
textarea {
  width: 100%;
  padding: 8px;
  margin-bottom: 10px;
}

button {
  padding: 10px 15px;
  font-size: 16px;
  cursor: pointer;
}

.error {
  color: red;
  font-size: 14px;
}
```

**Update the Main App Component**
Update `App.js` to include the Form component.

```javascript
import React from "react";
import Form from "./Form";
import "./App.css";

function App() {
  return (
    <div className="App">
      <h1>Contact Form</h1>
      <Form />
    </div>
  );
}

export default App;
```

# React Problem 5: Build a Todo List with Local Storage

## Problem Description

Create a Todo List application using React that includes the following functionalities:

1. **Add Todo**: Input a new todo item and add it to the list.
2. **Toggle Complete**: Mark a todo item as completed or not completed.
3. **Remove Todo**: Remove a todo item from the list.
4. **Persist Data**: Save the todo list to local storage and load it on app startup.

## Requirements

- Use functional components and hooks (`useState`, `useEffect`).
- Use local storage to persist the todo list.

## Solution

**Create the Todo Component:**
Create a `TodoApp` component that includes functionality to add, toggle, and remove todos. It should also handle local storage.

```javascript
import React, { useState, useEffect } from "react";
import "./TodoApp.css";

const TodoApp = () => {
  const [todos, setTodos] = useState([]);
  const [input, setInput] = useState("");

  useEffect(() => {
    const storedTodos = JSON.parse(localStorage.getItem("todos")) || [];
    setTodos(storedTodos);
  }, []);

  useEffect(() => {
    localStorage.setItem("todos", JSON.stringify(todos));
  }, [todos]);

  const addTodo = () => {
    if (input.trim()) {
      setTodos([...todos, { id: Date.now(), text: input, completed: false }]);
      setInput("");
    }
  };

  const toggleComplete = (id) => {
    setTodos(
      todos.map((todo) =>
        todo.id === id ? { ...todo, completed: !todo.completed } : todo
      )
    );
  };

  const removeTodo = (id) => {
    setTodos(todos.filter((todo) => todo.id !== id));
  };

  return (
    <div className="todo-app">
      <h1>Todo List</h1>
      <input
        type="text"
        value={input}
        onChange={(e) => setInput(e.target.value)}
        placeholder="Add a new todo"
      />
      <button onClick={addTodo}>Add</button>
      <ul>
        {todos.map((todo) => (
          <li
            key={todo.id}
            style={{ textDecoration: todo.completed ? "line-through" : "none" }}
          >
            {todo.text}
            <button onClick={() => toggleComplete(todo.id)}>
              {todo.completed ? "Undo" : "Complete"}
            </button>
            <button onClick={() => removeTodo(todo.id)}>Delete</button>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default TodoApp;
```

**Add Some Basic Styling:**
Create a `TodoApp.css` file for basic styling.

```css
.todo-app {
  max-width: 600px;
  margin: auto;
  text-align: center;
}

input {
  padding: 10px;
  font-size: 16px;
  margin-right: 10px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin: 10px 0;
}
```

**Update the Main App Component:**
Update `App.js` to include the TodoApp component.

```javascript
import React from "react";
import TodoApp from "./TodoApp";
import "./App.css";

function App() {
  return (
    <div className="App">
      <TodoApp />
    </div>
  );
}

export default App;
```
