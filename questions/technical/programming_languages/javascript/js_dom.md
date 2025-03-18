# JavaScript DOM (Document Object Model)

## 1. Introduction to DOM

- The **Document Object Model (DOM)** represents the structure of an HTML document as a tree.
- It allows JavaScript to manipulate HTML and CSS dynamically.

### Key Concepts:

- **Document**: Represents the entire HTML document.
- **Elements**: Represent HTML tags (e.g., `<div>`, `<p>`, `<button>`).
- **Nodes**: Every element, attribute, and piece of text in the DOM is a node.
- **Events**: Actions triggered by users (e.g., clicks, key presses).

---

## 2. Selecting Elements

We can select elements in various ways:

### 2.1 `getElementById()` (Select by ID)

```javascript
let element = document.getElementById("myId");
console.log(element);
```

### 2.2 `getElementsByClassName()` (Select by Class)

```javascript
let elements = document.getElementsByClassName("myClass");
console.log(elements[0]);
```

### 2.3 `getElementsByTagName()` (Select by Tag)

```javascript
let elements = document.getElementsByTagName("p");
console.log(elements[0]);
```

### 2.4 `querySelector()` (Select the First Matching Element)

```javascript
let element = document.querySelector(".myClass");
console.log(element);
```

### 2.5 `querySelectorAll()` (Select All Matching Elements)

```javascript
let elements = document.querySelectorAll("p");
console.log(elements);
```

---

## 3. Modifying Elements

### 3.1 Changing Text Content

```javascript
document.getElementById("myId").textContent = "New text";
```

### 3.2 Changing HTML Content

```javascript
document.getElementById("myId").innerHTML = "<strong>New HTML</strong>";
```

### 3.3 Changing CSS Styles

```javascript
document.getElementById("myId").style.color = "red";
```

### 3.4 Adding and Removing Classes

```javascript
document.getElementById("myId").classList.add("newClass");
document.getElementById("myId").classList.remove("oldClass");
```

---

## 4. Creating and Removing Elements

### 4.1 Creating an Element

```javascript
let newElement = document.createElement("div");
newElement.textContent = "Hello!";
document.body.appendChild(newElement);
```

### 4.2 Removing an Element

```javascript
let element = document.getElementById("myId");
element.remove();
```

---

## 5. Event Handling

### 5.1 Adding an Event Listener

```javascript
document.getElementById("myButton").addEventListener("click", function () {
  alert("Button clicked!");
});
```

### 5.2 Removing an Event Listener

```javascript
function myFunction() {
  alert("Event removed!");
}
let btn = document.getElementById("myButton");
btn.addEventListener("click", myFunction);
btn.removeEventListener("click", myFunction);
```

---

## 6. Common DOM Interview Questions and Answers

1. **What is the DOM?**  
   **Answer:** The DOM (Document Object Model) is a tree structure that represents an HTML document, allowing JavaScript to manipulate elements dynamically.

2. **How do you select an element by ID in JavaScript?**  
   **Answer:** Using `document.getElementById("id")`.

   ```javascript
   let element = document.getElementById("myId");
   ```

3. **What is the difference between `innerHTML` and `textContent`?**  
   **Answer:**

   - `innerHTML` sets or returns the HTML content inside an element (including tags).
   - `textContent` only sets or returns the text inside an element (ignores HTML tags).

4. **How do you add an event listener in JavaScript?**  
   **Answer:** Using `addEventListener()`.

   ```javascript
   document.getElementById("myButton").addEventListener("click", function () {
     alert("Button clicked!");
   });
   ```

5. **What is `querySelectorAll()` used for?**  
   **Answer:** It selects all elements that match a specified CSS selector and returns a NodeList.

   ```javascript
   let elements = document.querySelectorAll("p");
   ```

6. **How do you create and append an element in the DOM?**  
   **Answer:** Using `createElement()` and `appendChild()`.

   ```javascript
   let newDiv = document.createElement("div");
   newDiv.textContent = "Hello!";
   document.body.appendChild(newDiv);
   ```

7. **How do you remove an element from the DOM?**  
   **Answer:** Using `.remove()`.

   ```javascript
   document.getElementById("myId").remove();
   ```

8. **What is the difference between `nodeList` and `HTMLCollection`?**  
   **Answer:**

   - `NodeList`: A static or live collection of nodes (e.g., `querySelectorAll()` returns a static NodeList).
   - `HTMLCollection`: A live collection of elements (e.g., `getElementsByClassName()` returns an HTMLCollection).

9. **What is event delegation?**  
   **Answer:** Event delegation allows us to handle events efficiently by attaching an event listener to a parent element instead of each child.

   ```javascript
   document
     .getElementById("parent")
     .addEventListener("click", function (event) {
       if (event.target.tagName === "BUTTON") {
         alert("Button clicked!");
       }
     });
   ```

10. **How can you stop event propagation?**  
    **Answer:** Using `event.stopPropagation()`.

```javascript
document.getElementById("child").addEventListener("click", function (event) {
  event.stopPropagation();
  alert("Child clicked!");
});
```
