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

### 15. Explain the concept of the Document Object Model (DOM).

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

### 38. How do you create a drop-down list in HTML?

**Answer:**
A drop-down list is created using the `<select>` element, with `<option>` elements inside it. Example:

```html
<select>
  <option value="option1">Option 1</option>
  <option value="option2">Option 2</option>
  <option value="option3">Option 3</option>
</select>
```

### 39. What is the purpose of the `<details>` and `<summary>` elements in HTML5?

**Answer:**
The `<details>` element is used to create a disclosure widget from which the user can retrieve additional information or controls. The `<summary>` element is used as a summary or caption for the `<details>` content. Example:

```html
<details>
  <summary>More info</summary>
  <p>Additional information...</p>
</details>
```

### 40. What is the difference between `<b>` and `<strong>`, and between `<i>` and `<em>`?

**Answer:**

- **`<b>`:** Represents bold text without any extra importance.
- **`<strong>`:** Represents important text, typically rendered in bold.
- **`<i>`:** Represents italic text without any extra importance.
- **`<em>`:** Represents emphasized text, typically rendered in italics.

### 41. How do you embed a video in HTML5?

**Answer:**
You can embed a video using the `<video>` element with src, controls, autoplay, loop, and muted attributes. Example:

```html
<video src="video.mp4" controls>
  Your browser does not support the video tag.
</video>
```

### 42. What is the purpose of the download attribute in the `<a>` tag?

**Answer:**
The download attribute in the `<a>` tag specifies that the target should be downloaded when a user clicks on the hyperlink. Example:

```html
<a href="file.pdf" download>Download PDF</a>
```

### 43. How do you specify a default value for an input field in HTML?

**Answer:**
A default value for an input field is specified using the `value` attribute. Example:

```html
<input type="text" value="Default Value" />
```

### 44. Explain the use of the `defer` and `async` attributes in the `<script>` tag.

**Answer:**

- **`defer`**: Specifies that the script should be executed after the document has been parsed.
- **`async`**: Specifies that the script should be executed asynchronously as soon as it is available.

### 45. What is the purpose of the `<base>` tag in HTML?

**Answer:**  
The `<base>` tag specifies the base URL and/or target for all relative URLs in a document. It must be included inside the `<head>` element. Example:

```html
<base href="https://www.example.com/" target="_blank" />
```

### 46. How do you create an ordered list and an unordered list in HTML?

**Answer:**

- **`Ordered list`:** Created using the `<ol>` tag with list items inside `<li>` tags. Example:

```html
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```

- **`Unordered list`:** Created using the `<ul>` tag with list items inside `<li>` tags. Example:

```html
<ul>
  <li>Item one</li>
  <li>Item two</li>
  <li>Item three</li>
</ul>
```

### 47. What is the `<address>` tag used for in HTML?

**Answer:**
The `<address>` tag defines contact information for the author/owner of a document or article. It is typically displayed in italics and can contain email addresses, URLs, physical addresses, etc. Example:

```html
<address>
  Written by <a href="mailto:webmaster@example.com">Jon Doe</a>.<br />
  Visit us at:<br />
  Example.com<br />
  Box 564, Disneyland<br />
  USA
</address>
```

### 48. How do you embed an audio file in HTML5?

**Answer:**
You can embed an audio file using the `<audio>` element with `src`, `controls`, `autoplay`, and `loop` attributes. Example:

```html
<audio src="audio.mp3" controls>
  Your browser does not support the audio element.
</audio>
```

### 49. What is the use of the rel attribute in the `<link>` tag?

**Answer:**
The rel attribute specifies the relationship between the current document and the linked resource. Example:

```html
<link rel="stylesheet" href="styles.css" />
<link rel="icon" href="favicon.ico" type="image/x-icon" />
```

### 50. Explain the concept of progressive enhancement in web development.

**Answer:**
Progressive enhancement is a strategy for web design that emphasizes core webpage content first. It involves building the most basic features and content first, ensuring accessibility and functionality across all browsers and devices, and then adding advanced features and functionalities that enhance user experience in more capable browsers.

### 51. What is the `autocomplete` attribute in form elements?

**Answer:**  
The `autocomplete` attribute specifies whether a form or input field should have autocomplete enabled. It can have values `on` or `off`. Example:

```html
<form autocomplete="off">
  <input type="text" name="username" autocomplete="on" />
</form>
```

### 52. How do you specify a language for an element's content?

**Answer:**  
You can specify a language for an element's content using the `lang` attribute. Example:

```html
<p lang="fr">Bonjour le monde!</p>
```

### 53. What is the difference between `<progress>` and `<meter>` elements?

**Answer:**

- `<progress>`: Represents the completion progress of a task. Example:

```html
<progress value="70" max="100"></progress>
```

- `<meter>`: Represents a scalar measurement within a known range, such as disk usage. Example:

```html
<meter value="2" min="0" max="10">2 out of 10</meter>
```

### 54. How do you create a tooltip in HTML?

**Answer:**  
You can create a tooltip using the `title` attribute on an HTML element. Example:

```html
<button title="Click to submit">Submit</button>
```

### 55. What is the `required` attribute in form elements?

**Answer:**  
The `required` attribute specifies that an input field must be filled out before submitting the form. Example:

```html
<input type="text" name="username" required />
```

### 56. Explain the `hidden` attribute in HTML5.

**Answer:**  
The `hidden` attribute is used to hide an element from the user. It does not display the element, but the element is still available in the DOM. Example:

```html
<p hidden>This paragraph is hidden.</p>
```

### 57. What is the purpose of the `step` attribute in input elements?

**Answer:**  
The `step` attribute specifies the legal number intervals for an `<input>` element. Example:

```html
<input type="number" name="quantity" step="1" min="1" max="10" />
```

### 58. How do you make an image a clickable link in HTML?

**Answer:**  
You can make an image a clickable link by wrapping the `<img>` element inside an `<a>` element. Example:

```html
<a href="https://www.example.com">
  <img src="image.jpg" alt="Example Image" />
</a>
```

### 59. What is the purpose of the `<wbr>` tag in HTML5?

**Answer:**  
The `<wbr>` (Word Break Opportunity) tag specifies a point in text where a line break may occur. It helps control text wrapping. Example:

```html
<p>This is a verylongword<wbr />that should break here.</p>
```

### 60. How do you create a checkbox in HTML?

**Answer:**  
A checkbox is created using the `<input>` element with `type="checkbox"`. Example:

```html
<input type="checkbox" name="subscribe" value="newsletter" /> Subscribe to
newsletter
```

### 61. What is the `pattern` attribute in form elements?

**Answer:**  
The `pattern` attribute specifies a regular expression that the input field's value must match for the form to be submitted. Example:

```html
<input
  type="text"
  name="zipcode"
  pattern="[0-9]{5}"
  title="Five digit zip code"
/>
```

### 62. How do you create a radio button group in HTML?

**Answer:**  
A radio button group is created using multiple `<input>` elements with `type="radio"` and the same `name` attribute. Example:

```html
<form>
  <input type="radio" name="gender" value="male" /> Male
  <input type="radio" name="gender" value="female" /> Female
</form>
```

### 63. What is the purpose of the `<kbd>` tag in HTML?

**Answer:**  
The `<kbd>` tag represents user input, typically from a keyboard. Example:

```html
<p>Press <kbd>Ctrl</kbd> + <kbd>C</kbd> to copy.</p>
```

### 64. How do you create a line break in HTML?

**Answer:**  
A line break is created using the `<br>` tag. Example:

```html
<p>This is the first line.<br />This is the second line.</p>
```

### 65. Explain the purpose of the `<mark>` tag in HTML5.

**Answer:**  
The `<mark>` tag is used to highlight text for reference or notation. Example:

```html
<p>This is <mark>highlighted</mark> text.</p>
```

### 66. How do you specify that an input field should be in focus when the page loads?

**Answer:**  
You can specify that an input field should be in focus when the page loads using the `autofocus` attribute. Example:

```html
<input type="text" name="name" autofocus />
```

### 67. What is the `target` attribute in the `<a>` tag?

**Answer:**  
The `target` attribute specifies where to open the linked document. Common values include:

- `_self`: Default. Opens in the same frame.
- `_blank`: Opens in a new tab or window.
- `_parent`: Opens in the parent frame.
- `_top`: Opens in the full body of the window.
  Example:

```html
<a href="https://www.example.com" target="_blank">Visit Example</a>
```

### 68. How do you create a text area in HTML?

**Answer:**  
A text area is created using the `<textarea>` element. Example:

```html
<textarea name="comments" rows="4" cols="50">
Enter your comments here...</textarea
>
```

### 69. What is the purpose of the `novalidate` attribute in a form element?

**Answer:**  
The `novalidate` attribute specifies that the form should not be validated when submitted. Example:

```html
<form novalidate>
  <input type="text" name="name" required />
  <button type="submit">Submit</button>
</form>
```

### 70. Explain the difference between `width` and `max-width` in CSS.

**Answer:**

- `width`: Sets a fixed width for an element.
- `max-width`: Sets a maximum width for an element. If the content is smaller, it will take its natural width. If the content is larger, it will shrink to fit within the `max-width`.

### 71. How do you create a nested list in HTML?

**Answer:**  
A nested list is created by placing one list inside another. Example:

```html
<ul>
  <li>Item 1
    <

ul>
      <li>Sub-item 1</li>
      <li>Sub-item 2</li>
    </ul>
  </li>
  <li>Item 2</li>
</ul>
```

### 72. What is the purpose of the `<samp>` tag in HTML?

**Answer:**  
The `<samp>` tag is used to define sample output from a computer program. Example:

```html
<p>The output was: <samp>Error: Not found.</samp></p>
```

### 73. How do you create a definition list in HTML?

**Answer:**  
A definition list is created using the `<dl>` tag, with terms inside `<dt>` tags and descriptions inside `<dd>` tags. Example:

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

### 74. What is the purpose of the `<fieldset>` and `<legend>` tags in HTML?

**Answer:**

- `<fieldset>`: Groups related elements in a form.
- `<legend>`: Provides a caption for the `<fieldset>`.
  Example:

```html
<fieldset>
  <legend>Personal Information</legend>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" />
</fieldset>
```

### 75. Explain the use of the `for` attribute in the `<label>` tag.

**Answer:**  
The `for` attribute in the `<label>` tag specifies which form element the label is bound to. It should match the `id` of the associated input element. Example:

```html
<label for="email">Email:</label> <input type="email" id="email" name="email" />
```

### 76. What is the purpose of the `<output>` element in HTML5?

**Answer:**  
The `<output>` element represents the result of a calculation or user action. Example:

```html
<form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
  <input type="range" id="a" value="50" /> +
  <input type="number" id="b" value="50" />
  = <output name="result" for="a b">100</output>
</form>
```

### 77. How do you create a table in HTML?

**Answer:**  
A table is created using the `<table>` element, with rows defined by `<tr>`, headers by `<th>`, and data cells by `<td>`. Example:

```html
<table>
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Data 1</td>
    <td>Data 2</td>
  </tr>
  <tr>
    <td>Data 3</td>
    <td>Data 4</td>
  </tr>
</table>
```

### 78. What is the purpose of the `cite` attribute in the `<blockquote>` and `<q>` tags?

**Answer:**  
The `cite` attribute provides a URL that designates the source of the quotation. Example:

```html
<blockquote cite="https://www.example.com/article">
  This is a blockquote with a citation.
</blockquote>
<q cite="https://www.example.com/quote"
  >This is an inline quote with a citation.</q
>
```

### 79. How do you create a collapsible section in HTML5?

**Answer:**  
You can create a collapsible section using the `<details>` element, with a summary provided by the `<summary>` element. Example:

```html
<details>
  <summary>Click to expand</summary>
  <p>This is the content inside the collapsible section.</p>
</details>
```

### 80. What is the `contenteditable` attribute in HTML5?

**Answer:**  
The `contenteditable` attribute specifies whether the content of an element is editable or not. Example:

```html
<div contenteditable="true">This text is editable.</div>
```

### 81. Explain the use of the `spellcheck` attribute in HTML5.

**Answer:**  
The `spellcheck` attribute specifies whether the element is to have its spelling and grammar checked. It can be set to `true` or `false`. Example:

```html
<textarea spellcheck="true">This textarea has spell check enabled.</textarea>
```

### 82. How do you include an SVG image in an HTML document?

**Answer:**  
You can include an SVG image using the `<img>` tag, `<object>` tag, `<embed>` tag, or inline SVG. Examples:

```html
<img src="image.svg" alt="SVG Image" />
<object data="image.svg" type="image/svg+xml"></object>
<embed src="image.svg" type="image/svg+xml" />
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="red" />
</svg>
```

### 83. What is the purpose of the `accesskey` attribute in HTML5?

**Answer:**  
The `accesskey` attribute specifies a shortcut key to activate/focus an element. Example:

```html
<button accesskey="s">Press Alt + S to submit</button>
```

### 84. How do you create an email link in HTML?

**Answer:**  
An email link is created using the `<a>` tag with the `href` attribute set to `mailto:` followed by the email address. Example:

```html
<a href="mailto:example@example.com">Send Email</a>
```

### 85. What is the purpose of the `draggable` attribute in HTML5?

**Answer:**  
The `draggable` attribute specifies whether an element is draggable or not. Example:

```html
<p draggable="true">Drag this paragraph.</p>
```

### 86. Explain the use of the `sandbox` attribute in the `<iframe>` tag.

**Answer:**  
The `sandbox` attribute enables an extra set of restrictions for the content in the `<iframe>`. It can have various values like `allow-same-origin`, `allow-scripts`, `allow-forms`, etc. Example:

```html
<iframe src="example.html" sandbox="allow-scripts"></iframe>
```

### 87. How do you specify a custom icon for a website in HTML?

**Answer:**  
A custom icon for a website is specified using the `<link>` tag with `rel="icon"` and the `href` attribute pointing to the icon file. Example:

```html
<link rel="icon" href="favicon.ico" type="image/x-icon" />
```

### 88. What is the purpose of the `<noscript>` tag in HTML?

**Answer:**  
The `<noscript>` tag defines an alternate content to be displayed if a browser does not support scripting or if scripting is disabled. Example:

```html
<noscript>
  <p>This content is displayed if JavaScript is disabled.</p>
</noscript>
```

### 89. How do you create a multiline text input field in HTML?

**Answer:**  
A multiline text input field is created using the `<textarea>` element. Example:

```html
<textarea rows="4" cols="50">Enter your text here...</textarea>
```

### 90. Explain the use of the `pre` tag in HTML.

**Answer:**  
The `<pre>` tag is used to define preformatted text. Text inside this element is displayed in a fixed-width font, and whitespace is preserved. Example:

```html
<pre>
  This is
    preformatted
  text.
</pre>
```

### 91. What is the purpose of the `download` attribute in the `<a>` tag?

**Answer:**  
The `download` attribute specifies that the target will be downloaded when a user clicks on the hyperlink. Example:

```html
<a href="file.pdf" download>Download PDF</a>
```

### 92. How do you create a table with a caption in HTML?

**Answer:**  
A table with a caption is created using the `<table>` element with a `<caption>` element inside it. Example:

```html
<table>
  <caption>
    Table Caption
  </caption>
  <tr>
    <th>Header 1</th>
    <th>Header 2</th>
  </tr>
  <tr>
    <td>Data 1</td>
    <td>Data 2</td>
  </tr>
</table>
```

### 93. What is the purpose of the `data-*` attributes in HTML5?

**Answer:**  
The `data-*` attributes are used to store custom data private to the page or application. They can be used to store data that can be accessed by JavaScript. Example:

```html
<div data-user-id="12345">User Data</div>
```

### 94. How do you create a radio button group in HTML?

**Answer:**  
A radio button group is created using multiple `<input>` elements with `type="radio"` and the same `name` attribute. Example:

```html
<form>
  <input type="radio" name="gender" value="male" /> Male
  <input type="radio" name="gender" value="female" /> Female
</form>
```

### 95. What is the purpose of the `aria-*` attributes in HTML?

**Answer:**  
The `aria-*` attributes are part of the Accessible Rich Internet Applications (ARIA) specification and are used to increase the accessibility of web content by providing additional information to screen readers. Examples include `aria-label`, `aria-hidden`, and `aria-live`.

### 96. How do you create a dropdown menu in HTML?

**Answer:**  
A dropdown menu is created using the `<select>` element with `<option>` elements inside it. Example:

```html
<select>
  <option value="option1">Option 1</option>
  <option value="option2">Option 2</option>
  <option value="option3">Option 3</option>
</select>
```

### 97. What is the `formaction` attribute in HTML5?

**Answer:**  
The `formaction` attribute specifies the URL to send the form data to when the form is submitted. It can be used with `<button>` and `<input>` elements of type `submit` or `image`. Example:

```html
<form>
  <button type="submit" formaction="submit_page.php">Submit</button>
</form>
```

### 98. Explain the use of the `<bdo>` tag in HTML.

**Answer:**  
The `<bdo>` (bidirectional override) tag is used to override the current text direction. Example:

```html
<p><bdo dir="rtl">This text will be displayed right-to-left.</bdo></p>
```

### 99. How do you create a number input field in HTML5?

**Answer:**  
A number input field is created using the `<input>` element with `type="number"`. Example:

```html
<input type="number" name="quantity" min="1" max="10" />
```

### 100. What is the purpose of the `<abbr>` tag in HTML?

**Answer:**  
The `<abbr>` tag represents an abbreviation or acronym and is used to provide the full form of the abbreviation via the `title` attribute. Example:

```html
<abbr title="HyperText Markup Language">HTML</abbr>
```

### 101. What is the difference between the `<section>` and `<article>` tags in HTML5?

**Answer:**

- `<section>`: Represents a thematic grouping of content, typically with a heading. It is used to group related content together.
- `<article>`: Represents a self-contained piece of content that can be independently distributed or reused, such as a blog post or news article.

Example:

```html
<section>
  <h1>News</h1>
  <article>
    <h2>Breaking News</h2>
    <p>Details about the news...</p>
  </article>
</section>
```

### 102. What is the use of the `async` and `defer` attributes in the `<script>` tag?

**Answer:**

- `async`: The script is fetched asynchronously and executed as soon as it is available. It does not block the HTML parser.
- `defer`: The script is fetched asynchronously but executed only after the HTML document has been fully parsed.

Example:

```html
<script src="script.js" async></script>
<script src="script.js" defer></script>
```

### 103. How do you include external CSS styles in an HTML document?

**Answer:**  
External CSS styles are included using the `<link>` tag within the `<head>` section of the HTML document. Example:

```html
<link rel="stylesheet" href="styles.css" />
```

### 104. Explain the use of the `target="_self"` attribute in the `<a>` tag.

**Answer:**  
The `target="_self"` attribute specifies that the linked document should open in the same frame or window as the link. It is the default behavior, so it is often omitted.

Example:

```html
<a href="https://www.example.com" target="_self">Open in the same window</a>
```

### 105. How do you create a link that opens in a new window or tab?

**Answer:**  
You can create a link that opens in a new window or tab by using the `target="_blank"` attribute in the `<a>` tag. Example:

```html
<a href="https://www.example.com" target="_blank">Open in a new tab</a>
```

### 106. What is the purpose of the `<script>` tag in HTML?

**Answer:**  
The `<script>` tag is used to define client-side JavaScript code or include external JavaScript files in an HTML document. Example:

```html
<script>
  console.log("Hello, world!");
</script>
<script src="script.js"></script>
```

### 107. How do you specify that a form should be submitted using a POST method?

**Answer:**  
You specify that a form should be submitted using the POST method by setting the `method` attribute of the `<form>` tag to `post`. Example:

```html
<form action="submit_form.php" method="post">
  <input type="text" name="username" />
  <button type="submit">Submit</button>
</form>
```

### 108. What is the purpose of the `<meta>` tag in the `<head>` section of an HTML document?

**Answer:**  
The `<meta>` tag provides metadata about the HTML document, such as character encoding, viewport settings, and search engine information. Example:

```html
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="description" content="A description of the page." />
```

### 109. How do you create a form input that accepts only numeric values?

**Answer:**  
You create a form input that accepts only numeric values by using the `type="number"` attribute in the `<input>` tag. Example:

```html
<input type="number" name="quantity" min="1" max="100" />
```

### 110. What is the purpose of the `<iframe>` element in HTML?

**Answer:**  
The `<iframe>` element is used to embed another HTML document within the current document. It can be used to display content from other sources or applications. Example:

```html
<iframe src="https://www.example.com" width="600" height="400"></iframe>
```

### 111. How do you specify the character encoding for an HTML document?

**Answer:**  
You specify the character encoding for an HTML document using the `<meta>` tag with the `charset` attribute. Example:

```html
<meta charset="UTF-8" />
```

### 112. What is the `placeholder` attribute used for in form inputs?

**Answer:**  
The `placeholder` attribute provides a hint or example of the expected input within a form field. It is displayed within the input field until the user types something. Example:

```html
<input type="text" name="username" placeholder="Enter your username" />
```

### 113. How do you create a multi-line text area in HTML?

**Answer:**  
A multi-line text area is created using the `<textarea>` element, with attributes for rows and columns specifying its size. Example:

```html
<textarea rows="5" cols="40">Default text...</textarea>
```

### 114. What is the `name` attribute used for in HTML forms?

**Answer:**  
The `name` attribute is used to identify form elements and their data when the form is submitted. It is used to reference the form field's data on the server-side.

Example:

```html
<input type="text" name="email" />
```

### 115. Explain the `srcset` attribute in the `<img>` tag.

**Answer:**  
The `srcset` attribute provides a set of images to the browser, allowing it to choose the most appropriate image based on the device’s screen resolution or viewport size. Example:

```html
<img
  src="small.jpg"
  srcset="medium.jpg 768w, large.jpg 1200w"
  alt="Responsive Image"
/>
```

### 116. How do you create a hidden field in an HTML form?

**Answer:**  
A hidden field is created using the `<input>` element with `type="hidden"`. It is not visible to the user but can be used to store data sent with the form. Example:

```html
<input type="hidden" name="user_id" value="12345" />
```

### 117. What is the `rel` attribute used for in the `<link>` tag?

**Answer:**  
The `rel` attribute specifies the relationship between the current document and the linked resource. Common values include `stylesheet` for CSS files, `icon` for favicons, etc. Example:

```html
<link rel="stylesheet" href="styles.css" />
<link rel="icon" href="favicon.ico" />
```

### 118. How do you create a link that opens a new email message?

**Answer:**  
A link that opens a new email message is created using the `mailto:` scheme in the `href` attribute of the `<a>` tag. Example:

```html
<a href="mailto:example@example.com">Email Us</a>
```

### 119. What is the `autocomplete` attribute used for in HTML forms?

**Answer:**  
The `autocomplete` attribute specifies whether the browser should automatically complete input fields based on previous entries. It can be set to `on` or `off`. Example:

```html
<form autocomplete="on">
  <input type="text" name="username" />
</form>
```

### 120. How do you define a key-value pair in a definition list?

**Answer:**  
In a definition list, key-value pairs are defined using `<dt>` for the term and `<dd>` for the definition. Example:

```html
<dl>
  <dt>Term</dt>
  <dd>Definition of the term.</dd>
</dl>
```
