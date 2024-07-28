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

**App Component**
Create the main `App` component which will manage the state and render other components.

```javascript
// src/App.js
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

**TodoForm Component**
Create a form component to add new todos.

```javascript
// src/TodoForm.js
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

**TodoList Component**
Create a component to display the list of todos.

```javascript
// src/TodoList.js
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
