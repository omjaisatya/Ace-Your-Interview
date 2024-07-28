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
