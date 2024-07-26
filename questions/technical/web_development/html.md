# HTML Interview Questions and Answers

### 1. What is HTML?

**Answer:**  
HTML (HyperText Markup Language) is the standard markup language for creating web pages and web applications. It describes the structure of a web page semantically and originally included cues for the appearance of the document.

### 2. What are tags in HTML?

**Answer:**  
Tags are the fundamental building blocks of HTML. They define how elements should be displayed in the web browser. Tags are usually paired, with an opening tag (e.g., `<p>`) and a closing tag (e.g., `</p>`), although some tags are self-closing (e.g., `<img />`).

### 3. What is the difference between HTML and XHTML?

**Answer:**  
HTML is the standard markup language, while XHTML (Extensible Hypertext Markup Language) is a stricter, XML-based version of HTML. XHTML requires all elements to be properly closed, nested, and written in lowercase.

### 4. What is a semantic HTML element?

**Answer:**  
Semantic HTML elements clearly describe their meaning in a human- and machine-readable way. Examples include `<article>`, `<footer>`, `<header>`, `<nav>`, and `<section>`.

### 5. How do you include CSS in an HTML document?

**Answer:**  
CSS can be included in an HTML document in three ways:

- Inline: using the `style` attribute inside HTML elements (e.g., `<p style="color: red;">Text</p>`).
- Internal: using a `<style>` element within the `<head>` section of the HTML document.
- External: linking to an external CSS file using the `<link>` element within the `<head>` section.

### 6. What is the purpose of the `<!DOCTYPE html>` declaration?

**Answer:**  
The `<!DOCTYPE html>` declaration defines the document type and version of HTML being used. It ensures that the web browser renders the page in standards mode, which helps maintain consistency across different browsers.

### 7. Explain the difference between `<div>` and `<span>`.

**Answer:**

- `<div>`: A block-level element used to group larger sections of content. It starts on a new line and takes up the full width available.
- `<span>`: An inline element used to group smaller portions of text or other inline elements. It does not start on a new line and only takes up as much width as necessary.

### 8. What is the role of the `alt` attribute in the `<img>` tag?

**Answer:**  
The `alt` attribute provides alternative text for an image, which is displayed if the image cannot be loaded. It is also used by screen readers to describe the image to visually impaired users, improving accessibility.

### 9. How do you create a hyperlink in HTML?

**Answer:**  
A hyperlink is created using the `<a>` (anchor) element with the `href` attribute specifying the URL. For example:

```html
<a href="https://www.example.com">Visit Example</a>
```

### 10. What is the purpose of the <head> section in an HTML document?

**Answer:**
The <head> section contains meta-information about the HTML document, such as the title, character set, styles, scripts, and other meta tags. This information is not displayed directly on the web page.

### 11. Describe the `<table>` element and its sub-elements.

**Answer:**
The `<table>` element defines a table in HTML. Its sub-elements include:

- `<tr>`: Table row.
- `<td>`: Table data cell.
- `<th>`: Table header cell.
- `<thead>`: Group of header rows.
- `<tbody>`: Group of body rows.
- `<tfoot>`: Group of footer rows.

### 12. What is the difference between id and class attributes?

**Answer:**

- `id`: Uniquely identifies a single element within the HTML document. An id must be unique.
- `class`: Used to classify multiple elements. Multiple elements can share the same class.

### 13. How do you include JavaScript in an HTML document?

**Answer:**
JavaScript can be included in an HTML document in three ways:

- Inline: using the `onclick` attribute within HTML elements (e.g., `<button onclick="alert('Hello!')">Click Me</button>`).
- Internal: using a `<script>` element within the `<head>` or `<body>` section.
- External: linking to an external JavaScript file using the `<script src="path/to/file.js"></script>` element.

### 14. What is the `<meta>` tag used for?

**Answer:**
The `<meta>` tag provides metadata about the HTML document, such as character set, page description, keywords, author, and viewport settings. This information is used by browsers, search engines, and other web services.

## 15. Explain the concept of the Document Object Model (DOM).

**Answer:**
The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the page as a structured tree of objects, allowing scripts to dynamically access and manipulate the content, structure, and styles of a document.

### 16. What are data attributes in HTML5?

**Answer:**
Data attributes in HTML5 allow you to store extra information on HTML elements using custom attributes starting with data-. For example:

```html
<div data-user-id="12345">User</div>
```

These attributes can be accessed via JavaScript using the dataset property.

### 17. How do you create a form in HTML?

**Answer:**
A form is created using the `<form>` element, which can contain various input elements such as `<input>`, `<textarea>`, `<select>`, and `<button>`. For example:

```html
<form action="/submit" method="post">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" />
  <button type="submit">Submit</button>
</form>
```

### 18. What is the use of the `action` attribute in a form?

**Answer:**
The `action` attribute specifies the URL to which the form data will be submitted. If omitted, the form will be submitted to the same URL as the current page.

### 19. What is the purpose of the `method` attribute in a form?

**Answer:**
The `method` attribute specifies the HTTP method to use when submitting the form. Common values are `GET` (default) and `POST`. `GET` appends form data to the URL, while `POST` sends form data in the body of the request.

### 20. What is an `iframe` and how is it used?

**Answer:**
An iframe (`<iframe>`) is an HTML element used to embed another HTML document within the current document. For example:

```html
<iframe src="https://www.example.com" width="600" height="400"></iframe>
```

Iframes are commonly used for embedding videos, maps, and other external content.

### 21. What is the `<canvas>` element in HTML5?

**Answer:**  
The `<canvas>` element is used to draw graphics via scripting (usually JavaScript). It provides a drawable region defined in HTML code with height and width attributes.

### 22. Explain the difference between block-level and inline elements.

**Answer:**

- Block-level elements start on a new line and take up the full width available (e.g., `<div>`, `<p>`, `<h1>`).
- Inline elements do not start on a new line and only take up as much width as necessary (e.g., `<span>`, `<a>`, `<img>`).

### 23. What are HTML entities and why are they used?

**Answer:**  
HTML entities are used to display reserved characters in HTML. For example, `&lt;` is used to display `<` and `&amp;` is used for `&`. They ensure that special characters are correctly interpreted by the browser.

### 24. What is the purpose of the `lang` attribute in the `<html>` tag?

**Answer:**  
The `lang` attribute specifies the language of the document. It helps search engines and browsers understand the language in which the page is written, improving accessibility and search relevance. Example: `<html lang="en">`.

### 25. Describe the purpose of the `<link>` element in HTML.

**Answer:**  
The `<link>` element is used to define a relationship between the current document and an external resource. Commonly, it is used to link to external stylesheets. Example:

```html
<link rel="stylesheet" href="styles.css" />
```

### 26. How can you specify alternative text for multimedia content in HTML5?

**Answer:**
For images, use the alt attribute in the `<img>` tag. For video and audio, use the `<track>` element to provide text tracks for captions, subtitles, and other text-based content.

### 27. What are the new form input types introduced in HTML5?

**Answer:**
HTML5 introduced several new input types, including:

- `email`
- `url`
- `number`
- `range`
- `date`
- `month`
- `week`
- `time`
- `datetime-local`
- `search`
- `color`

### 28. What is the `<datalist>` element and how is it used?

**Answer:**
The `<datalist>` element contains a set of `<option>` elements that represent predefined options for an `<input>` element. It is used to provide an autocomplete feature. Example:

```html
<input list="browsers" name="browser" />
<datalist id="browsers">
  <option value="Chrome"></option>
  <option value="Firefox"></option>
  <option value="Safari"></option>
  <option value="Edge"></option>
</datalist>
```

### 29. What is the purpose of the `placeholder` attribute in an `<input>` element?

**Answer:**
The `placeholder` attribute provides a short hint that describes the expected value of an input field. It is displayed inside the input field when it is empty. Example:

```html
<input type="text" placeholder="Enter your name" />
```

### 30. Explain the difference between `localStorage` and `sessionStorage`.

**Answer:**

- `localStorage`: Stores data with no expiration date. The data is not deleted when the browser is closed and is available across sessions.
- `sessionStorage`: Stores data for the duration of the page session. The data is deleted when the page session ends, which usually happens when the browser or tab is closed.

### 31. What is the `<noscript>` element used for?

**Answer:**
The `<noscript>` element defines an alternate content to be displayed if the browser does not support scripting or if scripting is disabled. It provides a fallback for users without JavaScript.

### 32. How do you use the `<figure>` and `<figcaption>` elements?

**Answer:**
The `<figure>` element is used to group media content like images, diagrams, or code snippets, along with their captions. The `<figcaption>` element provides a caption for the `<figure>`. Example:

```html
<figure>
  <img src="image.jpg" alt="Description" />
  <figcaption>Image description</figcaption>
</figure>
```

### 33. What is a self-closing tag and can you give examples?

**Answer:**
A self-closing tag does not require a closing tag and is written with a slash at the end. Examples include `<img />`, `<br />`, `<hr />`, and `<input />`.

### 34. What is the use of the viewport meta tag in HTML5?

**Answer:**
The viewport meta tag controls the layout on mobile browsers. It helps to ensure the web page is responsive by setting the width and scale of the viewport. Example:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

### 35. How do you define a `section` of a document in HTML5?

**Answer:**
In HTML5, the `<section>` element is used to define sections of content, typically with a heading. It represents a thematic grouping of content, generally with a heading. Example:

```html
<section>
  <h2>Section Title</h2>
  <p>Section content...</p>
</section>
```

### 36. Explain the purpose of the `<template>` element in HTML5.

**Answer:**
The `<template>` element is used to declare HTML fragments that are not to be rendered immediately when the page loads. It is used for client-side templating. The content inside `<template>` is inert until it is activated by JavaScript.

### 37. What are the global attributes in HTML5?

**Answer:**
Global attributes can be used on any HTML element. They include:

- `class`
- `id`
- `style`
- `title`
- `data-*`
- `tabindex`
- `contenteditable`
- `lang`
- `dir`
