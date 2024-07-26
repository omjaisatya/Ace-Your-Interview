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

### 11. Describe the <table> element and its sub-elements.

**Answer:**
The <table> element defines a table in HTML. Its sub-elements include:

- <tr>: Table row.
- <td>: Table data cell.
- <th>: Table header cell.
- <thead>: Group of header rows.
- <tbody>: Group of body rows.
- <tfoot>: Group of footer rows.

### 12. What is the difference between id and class attributes?

**Answer:**

- `id`: Uniquely identifies a single element within the HTML document. An id must be unique.
- `class`: Used to classify multiple elements. Multiple elements can share the same class.
