# HTML/CSS Interview Questions and Answers

This document contains a collection of frontend interview questions with detailed answers, formatted with expandable sections for easy reference.

<details>
<summary>1. What is the purpose of semantic HTML? When and where is it important? </summary>
Semantic HTML provides meaning to the web page structure by using tags that reflect the purpose of the content inside them 
(`<article>`, `<section>`, `<header>`, etc.).

**Why it's important:**
- **Accessibility**: Helps screen readers and assistive technologies understand content structure.
- **SEO**: Search engines use semantic tags to better index and rank content.
- **Maintainability**: Easier for developers to read and update code.
- **Consistency**: Promotes a standardized way of building layouts.

**When and where to use:**  
Always prefer semantic tags when the content has a clear role or meaning. For example:
- Use `<nav>` for site navigation.
- Use `<article>` for blog posts or news entries.
- Use `<footer>` for contact info and legal disclaimers.
</details>

<details>
<summary>2. How can you style checkboxes in HTML/CSS? </summary>

```html
<label class="custom-checkbox">
  <input type="checkbox" />
  <span class="checkmark"></span>
  I agree to the terms
</label>
```

```css /* 1. Visually hide input but keep it accessible */ .custom-checkbox
input {
  position: absolute;
  opacity: 0;
  width: 0;
  height: 0;
} /* 2. Style the
visual checkbox box */
.custom-checkbox .checkmark {
  display: inline-block;
  width: 20px;
  height: 20px;
  border: 2px solid #333;
  border-radius: 4px;
  margin-right: 8px;
  vertical-align: middle;
  position: relative;
  transition: border-color 0.2s, background-color 0.2s;
} /* 3. Add the checkmark with ::after
when checked */
.custom-checkbox input:checked + .checkmark::after {
  content: '';
  position: absolute;
  left: 5px;
  top: 1px;
  width: 6px;
  height: 12px;
  border: solid white;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
} /* 4. Change
background color when checked */
.custom-checkbox input:checked + .checkmark {
  background-color: #333;
} /* 5. Focus indicator for keyboard users */
.custom-checkbox input:focus-visible + .checkmark {
  outline: 2px solid #005fcc;
  outline-offset: 2px;
} /* Optional: cursor + hover */
.custom-checkbox {
  cursor: pointer;
  user-select: none;
}
.custom-checkbox:hover .checkmark {
  border-color: #666;
}
```
</details>

<details>
<summary>3. What can a form consist of? What are the main attributes of a form and its elements, and what do they do? How to validate a form?</summary>

A form typically consists of the following elements:

- `<form>`: The container that wraps all form elements and defines the form action (where the data should be sent) and method (how the data should be sent, usually GET or POST).
- `<input>`: The most common form element, used for receiving user input (text, number, date, etc.).
- `<label>`: Provides a label for a form element, improving accessibility and usability by associating the label text with a specific input field.
- `<textarea>`: Used for multi-line text input (e.g., comments or messages).
- `<select>`: A dropdown menu for selecting one or more options from a list.
- `<button>`: Used to submit the form or trigger actions.
- `<fieldset>`: Groups related form elements together, often with a `<legend>` element for a title.

## Why bind a `<label>` to an `<input>`?

Using `<label>` elements correctly is important for both accessibility and user experience. Here's why:

1. **Accessibility for screen readers**  
   When a label is properly associated with an input (via the `for` attribute or by wrapping the input), screen readers announce the label text when the input is focused.  
   ➤ Without this, users with visual impairments won’t know what the input is for.

2. **Clickable area**  
   Binding a label to an input makes the label clickable, which means clicking the label will focus or toggle the input (e.g., toggles a checkbox or focuses a text field).  
   ➤ This improves UX, especially for small elements like checkboxes and radio buttons.

3. **Better semantic structure**  
   Associating labels with inputs improves the semantic correctness of your form.  
   ➤ It helps browsers and assistive technologies interpret and handle the form more effectively.

---

### Use cases:

- ✅ Use `<label>` for single input descriptions.
- ✅ Use `<fieldset>` + `<legend>` to group and describe sets of related inputs.


### Main attributes of form elements:

### For `<form>`:
- `action` – URL where the form data is sent after submission.
- `method` – HTTP method used (`GET` or `POST`).
- `target` – where to open the response (e.g., `_self`, `_blank`).
- `novalidate` – disables browser's built-in validation.

### For form elements:
- `name` – key used to identify the input’s data when the form is submitted.
- `value` – the current value of the input.
- `type` – defines the kind of input (`text`, `email`, `password`, `checkbox`, etc.).
- `required` – input must be filled out before submitting.
- `min`, `max`, `minlength`, `maxlength` – limit input range or length.
- `pattern` – regex to define custom input format.
- `placeholder` – text shown inside the input before user types.
- `readonly`, `disabled` – restrict editing or interaction.

### Form validation:

- **Client-side validation**: Done using HTML attributes (like `required`, `minlength`, `pattern`) or JavaScript to check input before submission.
- **Server-side validation**: Done on the server after form submission to ensure data integrity and security.
- **HTML5 validation**: Modern HTML provides built-in validation (e.g., for email, URL, or number inputs), but can be enhanced with JavaScript for custom checks.
</details>

<details>
  <summary>4. What is the difference between PNG and JPG? What are the advantages of SVG?</summary>
   PNG vs JPG:

### PNG (Portable Network Graphics):

- Lossless compression (no data is lost during compression).
- Supports transparency (alpha channel).
- Larger file sizes due to lossless compression.
- Best for images with text, logos, or images needing transparency.

### JPG (JPEG - Joint Photographic Experts Group):

- Lossy compression (some image data is lost during compression).
- Smaller file sizes compared to PNG.
- Does not support transparency.
- Ideal for photographs or images with gradients and lots of colors.

## Advantages of SVG (Scalable Vector Graphics):

- **Scalability**: SVG images are resolution-independent and can be scaled to any size without loss of quality, making them perfect for responsive designs.
- **Smaller file size**: For images that can be represented by vectors, SVG files tend to be smaller than raster images like PNG or JPG.
- **Editable**: SVG files can be edited with code, allowing for easy modification of elements (such as colors, shapes, and sizes) without needing a graphic editor.
- **Interactive**: SVG can be manipulated using CSS and JavaScript, allowing for animations and interactivity in web pages.
- **Accessibility**: Since SVGs are text-based, they can be indexed by search engines and are often more accessible than other formats.
</details>

<details>
<summary>What is the difference between PNG and JPG? What are the advantages of SVG?</summary>

### PNG vs JPG:

#### PNG (Portable Network Graphics):
- Lossless compression (no data is lost during compression).
- Supports transparency (alpha channel).
- Larger file sizes due to lossless compression.
- Best for images with text, logos, or images needing transparency.

#### JPG (JPEG - Joint Photographic Experts Group):
- Lossy compression (some image data is lost during compression).
- Smaller file sizes compared to PNG.
- Does not support transparency.
- Ideal for photographs or images with gradients and lots of colors.

### Advantages of SVG (Scalable Vector Graphics):
- **Scalability**: resolution-independent and scales without loss of quality.
- **Smaller file size**: compared to raster images.
- **Editable**: modifiable with code (CSS/JS).
- **Interactive**: supports animation and interactivity.
- **Accessibility**: text-based, indexable by search engines.

</details>


<details>
<summary>5. What issues can occur when using inline-blocks for layout, and how can we fix them? Where does the extra space between them come from?</summary>
✅ **Answer:**

### Issues with `inline-block` layout

When you use `display: inline-block` to place elements side by side, a **horizontal space (gap)** often appears between them — similar to the space between words in a sentence.

---

### 🔍 Why does the gap appear?

The gap is caused by **whitespace characters** (spaces, tabs, newlines) in the HTML between the elements. Inline-block elements are treated like inline text, so this whitespace is rendered as a visible gap.

Example:
```html
<div class="box"></div> <div class="box"></div>
```

✅ **Solutions to remove the gap:**

1. Remove whitespace in HTML

```html
<div class="box"></div><div class="box"></div>
```

2. Use HTML comments to hide the whitespace

```html
<div class="box"></div><!--
--><div class="box"></div>
```

3. Set `font-size: 0` on the container

```css
.container {
  font-size: 0;
}
```

4. Use Flexbox or CSS Grid instead These layout models are modern, more powerful, and do not suffer from this whitespace issue.

</details>

<details>
<summary>6. What does <code>flex-basis</code> and <code>flex-wrap</code> do?</summary>

### `flex-basis`

- Defines the **initial main size** of a flex item **before** any space is distributed.
- Can be set in `px`, `%`, `em`, etc.
- Default is `auto`, which means the size is based on the item’s content or `width`/`height` property.

**Example:**
```css
.item {
  flex-basis: 200px; /* item will start with 200px width */
}
```
`flex-wrap` Controls whether flex items should wrap onto multiple lines if there’s not enough space in one line.

Values:

- nowrap (default): all items stay on one line.
- wrap: items will wrap to the next line.
- wrap-reverse: wrap to the next line in reverse order.

Example:

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

</details> 

<details>
<summary>7. What’s the browser support situation for Flexbox and Grid? Where can you check it? What are vendor prefixes?</summary>

### 🧭 Browser Support

- **Flexbox** is supported in all modern browsers, including Chrome, Firefox, Edge, Safari, and even IE11 (with some limitations).
- **CSS Grid** is also supported in all modern browsers, **except Internet Explorer**, which only supports an older version (and partially).

💡 Always test for fallback or use feature queries (`@supports`) if you target legacy browsers.

---

### 🔍 Where to check support?

You can check browser compatibility for any CSS feature at:

➡️ [https://caniuse.com/](https://caniuse.com/)

Just search for "flexbox", "grid", or any other feature.

---

### 🏷️ Vendor Prefixes

**Vendor prefixes** are used to add support for CSS features that are experimental or not fully standardized.

They look like this:

- `-webkit-` for Chrome, Safari (WebKit engine)
- `-moz-` for Firefox (Mozilla)
- `-ms-` for Internet Explorer/Edge
- `-o-` for Opera (older versions)

**Example:**

```css
.box {
  -webkit-user-select: none; /* Safari */
  -moz-user-select: none;    /* Firefox */
  -ms-user-select: none;     /* IE10+ */
  user-select: none;         /* Standard */
}
```

✅ Tools like Autoprefixer (used with PostCSS) automatically add necessary prefixes based on your browser support target.

</details> 

<details>
<summary>8. What is BEM? What are blocks, elements, modifiers, and mixes?</summary>

### 📚 BEM = Block, Element, Modifier

BEM is a **CSS naming convention** designed to make class names more readable, reusable, and scalable. It stands for:

---

### 🔷 Block
A **standalone component** that is meaningful on its own.

- Represents a high-level component (e.g., `header`, `menu`, `button`).
- Class name: `block`

```html
<div class="menu"></div>
```

### 🧩 Element
A part of a block that has no standalone meaning and is semantically tied to its block.

Class name: block__element

```html
<div class="menu__item"></div>
```

### 🎛 Modifier
A variation of a `block` or `element` — it changes appearance, behavior, or state.
`Class name: block--modifier` or `block__element--modifier`

```html
<button class="button button--primary"></button>
<div class="menu__item menu__item--active"></div>
``` 

### 🧬 Mix
Combining multiple BEM classes on one element (e.g., from different blocks or modifiers).

```html
<div class="card card--highlighted promo__card"></div>
```
This element is:
A card with card--highlighted modifier
Also part of the promo block (promo__card)

✅ Benefits of BEM:
Predictable and consistent naming
Easier to read and maintain CSS
Avoids conflicts in large projects

</details> 

<details>
<summary>9. What is `<code>DOCTYPE</code>` and why is it used?</summary>

`<!DOCTYPE>` is a declaration used in HTML to specify the document type and the version of HTML that the web page uses. It must be placed at the very beginning of the HTML document, before the `<html>` tag.

### Why is DOCTYPE used?

**To define the HTML standard:**  
The DOCTYPE tells the browser which HTML version to use when interpreting the code. For modern web pages, we use `<!DOCTYPE html>`, which indicates HTML5.

### Browser rendering modes:

- **Standards mode:** If the correct DOCTYPE is declared, the browser renders the page according to modern web standards.
- **Quirks mode:** If the DOCTYPE is missing or incorrect, the browser may enter quirks mode (compatibility mode), where it renders the page using outdated rules, which can cause layout or styling issues.

### Example for HTML5:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Example</title>
  </head>
  <body>
    <h1>Hello, world!</h1>
  </body>
</html>
```

This declaration is short and universal for all HTML5 documents.

</details> 

<details>
<summary>What are the main tags used in the structure of an HTML page?</summary>

The basic structure of an HTML document includes the following key tags:

- `<!DOCTYPE html>`: Declares that the document uses HTML5.
- `<html>`: The root element that wraps all content of the page. It tells the browser this is an HTML document.
- `<head>`: Contains metadata about the page that isn’t displayed directly, such as titles, styles, and fonts.
- `<meta>`: Provides metadata like character encoding or page description for search engines.
- `<title>`: Sets the page title shown in the browser tab.
- `<link>`: Used to link external resources like CSS stylesheets.
- `<style>`: Includes internal CSS styles directly in the document.
- `<script>`: Allows the addition of JavaScript either inline or via external files.
- `<body>`: Contains all the visible content on the page such as text, images, buttons, etc.
- `<header>`: Represents the top section of the page, usually for headings or navigation.
- `<main>`: Contains the main content of the page.
- `<footer>`: Represents the bottom section with additional info like contact details or copyright.

### Example of a basic HTML structure:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <header>
      <h1>Welcome to My Website</h1>
    </header>
    <main>
      <p>This is the main content of the page.</p>
    </main>
    <footer>
      <p>&copy; 2024 My Website</p>
    </footer>
  </body>
</html>
```

This is the minimal structure required to ensure proper functioning of an HTML document.

</details>

<details>
<summary>What are semantic tags and why are they important? Provide examples.</summary>

**Semantic tags** are HTML elements that clearly define the meaning and purpose of the content they enclose. They describe not just the structure, but also the content itself, making it easier for browsers, search engines, and assistive technologies (like screen readers) to understand.

### Why use semantic tags?

- **Improved accessibility**: Assistive technologies can interpret the content more accurately.
- **Better SEO**: Search engines can index content more effectively based on its structure and meaning.
- **Improved code readability**: Semantic tags make it easier for developers to understand the document structure.
- **Standards compliance**: Using semantic HTML aligns with modern web development standards and ensures greater compatibility.

### Examples of semantic tags:

- `<header>`: Represents the top section of a page or a section (often contains navigation and headings).
- `<nav>`: Defines navigation links or menus.
- `<main>`: Contains the main content that is unique to the page.
- `<article>`: Represents a standalone piece of content, such as a blog post or article.
- `<section>`: Groups related content under a common theme, often with a heading.
- `<aside>`: Represents additional information, like a sidebar or related links.
- `<footer>`: Marks the bottom part of a page or section, typically with copyright or contact info.
- `<figure>`: Used for self-contained content like images or charts.
- `<figcaption>`: A caption or description for content inside a `<figure>`.

### Example using semantic tags:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Semantics Example</title>
  </head>
  <body>
    <header>
      <h1>My Website</h1>
      <nav>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <article>
        <h2>Article Title</h2>
        <p>This is the content of the article.</p>
      </article>

      <section>
        <h2>Related Section</h2>
        <p>This section is related to the main content.</p>
      </section>
    </main>

    <aside>
      <p>Additional info or advertisements</p>
    </aside>

    <footer>
      <p>&copy; 2024 My Website</p>
    </footer>
  </body>
</html>
```
Semantic tags make HTML more meaningful and structured, improving both user experience and search engine optimization.

</details>

<details>
<summary>10. What can you say about the &lt;br&gt; tag?</summary>

The `<br>` tag in HTML is used to insert a line break (text goes to the next line) inside text elements. It is a self-closing tag, meaning it does not have a closing counterpart.

### Key points about `<br>`:

- **Purpose**: It inserts a line break where text should start on a new line, without creating a new block like the `<p>` tag does.
  
- **Syntax**:

```html
<br>
```

or in a self-closing variant (rarely used, but valid in XHTML):

```html
<br />
Usage:
To separate lines of text without creating new paragraphs.
Used when you want the text to start from a new line without the extra indentation that paragraph tags typically add.
Useful for formatting poetry, addresses, or places where text structure is important.

### Example:

```html
<p>This is the first line.<br>This is the second line after the break.</p>
```
Result:
`This is the first line.
This is the second line after the break.`

### When not to use `<br>`:

If you need to format large blocks of text, it's better to use block-level tags like <p> for paragraphs or <div> for larger sections of content.

Instead of using <br> to add space between lines, CSS (e.g., margin or padding) should be used to control the appearance of text.

### Conclusion:

The `<br>` tag should be used for cases where a simple line break is needed, but it should not be used for structuring the page or formatting large text blocks. It is a small tool for specific scenarios.

</details> 

<details>
<summary>11. What is the difference between <code>&lt;div&gt;</code> and <code>&lt;span&gt;</code>?</summary>

The key difference between `<div>` and `<span>` tags lies in how they affect the page structure and the type of content they are meant to group.

---

### `<div>` — Block-level Element

- Occupies the full width of its container.
- Always starts on a new line.
- Used to group larger blocks of content or elements (usually block-level elements).
- Can contain both block-level and inline elements.

**Example:**

```html
<div>
  <h1>Title</h1>
  <p>This is a paragraph inside a div.</p>
</div>
```

**`<span>` — Inline Element**

Does not start on a new line.
Wraps only the portion of content it surrounds.
Used to group small parts of text or inline elements for styling or scripting.
Can only contain other inline elements.

```html
<p>This is a <span style="color: red;">highlighted</span> word in a paragraph.</p>
```

### When to Use

Use <div> to structure or organize large content sections (e.g., containers, layout blocks).
Use <span> for styling or handling small inline content (e.g., changing the color of a single word).
Both tags are commonly used with CSS and JavaScript to control the appearance and behavior of content.

</details> 

<details>
<summary>12. What are data attributes and in which cases do you use them?</summary>

**Data attributes** are special attributes in HTML that allow storing additional information directly in HTML elements. They start with the prefix `data-` and can be in any format suitable for storing information that can be used with JavaScript.

### Syntax of data attributes:

```html
<div data-user-id="123" data-role="admin">John Doe</div>
```

In this example:
* `data-user-id` stores the user ID.
* `data-role` stores the user's role.

### How to use:

Data attributes are typically used to transfer small pieces of data between HTML and JavaScript or CSS without the need for additional server requests or other mechanisms.

### Use cases:

1. **Passing data to JavaScript**: Used to access special information on the page through JavaScript. This can be convenient for working with UIs without making server requests.

**Example:**
```html
<div id="user" data-user-id="123" data-role="admin">John Doe</div>

<script>
  const userDiv = document.getElementById('user');
  const userId = userDiv.getAttribute('data-user-id');
  const userRole = userDiv.dataset.role;
  
  console.log(userId);  // 123
  console.log(userRole); // admin
</script>
```

2. **CSS selectors with data attributes**: You can style elements based on the values of `data-` attributes.

**Example:**
```html
<div data-status="active">Active User</div>
<div data-status="inactive">Inactive User</div>

<style>
  [data-status="active"] { color: green; }
  [data-status="inactive"] { color: red; }
</style>
```

3. **Storing temporary data for events**: When you want to store information that is only used on the frontend (e.g., during clicks on elements).

**Example**: You can store product information in a button:
```html
<button data-product-id="1001" data-product-price="25.99">Buy Now</button>

<script>
  const button = document.querySelector('button');
  button.addEventListener('click', () => {
    const productId = button.dataset.productId;
    const productPrice = button.dataset.productPrice;
    alert(`Product ID: ${productId}, Price: ${productPrice}`);
  });
</script>
```

4. **Instead of hidden fields**: Data attributes can be used to store information that is not displayed in the UI but is needed for working with JavaScript. They are an alternative to hidden form fields or other methods of data storage.

5. **Enabling dynamic interaction on the client**: Data attributes allow binding data to HTML elements that can dynamically change, and these changes can be tracked or processed through JavaScript.

### Advantages:
* Ease of use: no need to change database structure or server APIs to work with additional data.
* Readability and clarity: data is stored directly in HTML, making it easy to see and understand.
* Easy integration with JavaScript.

### Disadvantages:
* Data attributes are not suitable for storing large amounts of data.
* They should not be used to store confidential information, as this data is easily accessible in the HTML code and can be viewed by anyone.

### Conclusion:
Data attributes are a convenient tool for storing additional data that may be needed for frontend work, especially in cases where you want to avoid complex interactions with the server or databases.

</details>

<details>
<summary>13. How are class and id attributes used? What is the difference between classes and identifiers? </summary>

The `class` and `id` attributes are used in HTML to give elements unique or shared identifiers, which help style elements using CSS or manipulate them through JavaScript. While these attributes have similar functions, there are several key differences between them.

**Class Attribute**

1. **Purpose**: The `class` attribute is used to group multiple elements so that common styles or functionality can be applied to them. An element can have one or more classes, separated by spaces.

2. **Usage**:
   * **CSS**: Classes allow styles to be applied to groups of elements.
   * **JavaScript**: Used to reference groups of elements or to dynamically change classes.

**Example of using `class` in HTML**:
```html
<div class="content box">This is a content box</div>
<p class="content">This is a paragraph inside the content</p>
```

**CSS** for class:
```css
.content {
  font-size: 16px;
  color: blue;
}
.box {
  border: 1px solid black;
}
```

**JavaScript** for class:
```javascript
const elements = document.getElementsByClassName('content');
console.log(elements.length); // Returns the number of elements with class "content"
```

3. **Can be used for multiple elements**: The same class can be assigned to many elements on a page, allowing them to share common styles or functionality.

**ID Attribute**

1. **Purpose**: The `id` attribute is used to **uniquely** identify a single element on a page. An `id` must be unique for each element, meaning there cannot be two elements with the same `id` on a page.

2. **Usage**:
   * **CSS**: Used to style a specific element.
   * **JavaScript**: Used to access or manipulate a specific element.

**Example of using `id` in HTML**:
```html
<div id="header">This is the header</div>
```

**CSS** for identifier:
```css
#header {
  background-color: gray;
  font-size: 24px;
}
```

**JavaScript** for identifier:
```javascript
const header = document.getElementById('header');
console.log(header.textContent); // Outputs the text of the element with id "header"
```

3. **Uniqueness**: Each element should have a **unique** `id`. This is important because `id` is used to unambiguously identify an element.

**Main differences between `class` and `id`**:

| Characteristic | `class` | `id` |
|----------------|---------|------|
| **Uniqueness** | Can be assigned to many elements | Unique for each element |
| **Usage** | For grouping elements | For identifying a single element |
| **CSS Selector** | Period (`.`), e.g., `.content` | Hash mark (`#`), e.g., `#header` |
| **CSS Specificity** | Lower specificity (lower priority) | Higher specificity (higher priority) |
| **JavaScript** | `getElementsByClassName()` or `querySelectorAll()` | `getElementById()` or `querySelector()` |

**When to use**:
* Use `class` when you want to apply the same style or functionality to multiple elements.
* Use `id` when you need to identify a **specific** element, such as a header, form, or unique block.

Proper use of `class` and `id` helps structure HTML code, improves its readability, and makes it convenient for styling and interaction through JavaScript.
</details>

<details>
<summary>14. What are internal and external hyperlinks and what attributes do they have?</summary>

**Hyperlinks** in HTML are links to other resources or pages, created using the `<a>` tag. They can be **internal** (links to other pages or parts of the same site) or **external** (links to other websites). Both types of hyperlinks have attributes that provide functionality.

## 1. Internal Hyperlinks

**Internal hyperlinks** lead to other pages or sections within the same website.

Example:
```html
<a href="/about.html">About Us</a>
```

This is an example of an internal link that leads to "about.html" page located in the same directory of the site.

**Attributes:**
* `href`: mandatory attribute that specifies the path to the page or element. For internal hyperlinks, you can use relative paths:
   * `/page.html` (relative path to a page)
   * `#section` (link to a section on the current page)

**Example of an anchor** (internal link to a section):
```html
<a href="#contact">Contacts</a>
<div id="contact">
  <h2>Contact Information</h2>
</div>
```

In this example, the link leads to an element with `id="contact"` on the same page.

## 2. External Hyperlinks

**External hyperlinks** lead to other websites different from the current one.

Example:
```html
<a href="https://www.example.com">Visit example</a>
```

This is an external link that leads to the "example.com" website.

**Attributes:**
* `href`: specifies the full URL of the external resource (https://, http://)
* `target="_blank"`: opens the link in a new browser tab or window
* `rel="noopener noreferrer"`: used with `target="_blank"` to prevent potential security and performance issues (relates to control transfer between pages)

**Example with attributes** `target` and `rel`:
```html
<a href="https://www.google.com" target="_blank" rel="noopener noreferrer">Google</a>
```

In this case, the page will open in a new tab, and additional protection against external threats will be established.

## Main Attributes for Hyperlinks:

1. `href` — the main attribute that specifies the address where the link leads.
   * Internal: `/about.html`, `#section`
   * External: `https://example.com`

2. `target` — specifies how to open the link:
   * `_self`: opens the link in the same window (default value)
   * `_blank`: opens the link in a new tab or window

3. `rel` — used to define the relationship between the current page and the linked page. Usually used with the `target="_blank"` attribute to avoid potential security threats.
   * `noopener`: prevents the new tab from having access to the page from which the link was opened
   * `noreferrer`: does not transmit information about the page from which the transition was made

4. `title` — shows tooltip text when the user hovers over the link.
```html
<a href="https://example.com" title="Visit Example Site">Example</a>
```

## Conclusion:
* **Internal hyperlinks** are used for navigation between pages of one website.
* **External hyperlinks** lead to other websites.
* The main attribute of hyperlinks is `href`, while additional attributes such as `target` and `rel` are used to define link behavior.
</details>

<details>
<summary>15. What do you know about SVG? What are the options for adding SVG to website pages? How do they differ?</summary>

**SVG (Scalable Vector Graphics)** is a vector graphic format used to display two-dimensional graphics on web pages. SVG is based on XML, which allows both simple and complex vector images to be described using code. The main advantages of SVG are:

* **Scalability**: SVG images don't lose quality when resized, making them ideal for responsive design.
* **Editability**: SVG can be edited directly in a text editor since it's a text-based format.
* **Animation**: SVG supports animations and interactivity through CSS and JavaScript.
* **SEO-friendly**: SVG graphics can be indexed by search engines, which improves SEO.

## Options for Adding SVG to Website Pages

### 1. Inserting SVG Code Directly into HTML

```html
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" />
</svg>
```

* **Advantages**:
  * Easy access to styling and animation through CSS and JavaScript.
  * All SVG elements are available for manipulation.
* **Disadvantages**:
  * Can increase the size of HTML code if the image is complex.

### 2. Using the `<img>` Tag

```html
<img src="image.svg" alt="Description of image" />
```

* **Advantages**:
  * Simple to use; suitable for basic SVG images.
  * Appropriate for cases where interaction with SVG content is not needed.
* **Disadvantages**:
  * Limited access to styling and animation since the SVG is not part of the DOM.

### 3. Using the `<object>` Tag

```html
<object type="image/svg+xml" data="image.svg">Your browser does not support SVG</object>
```

* **Advantages**:
  * Can be used to connect SVG that contains embedded scripts and styles.
  * If SVG is not supported, alternative text can be specified.
* **Disadvantages**:
  * Doesn't always provide access to the DOM for manipulation.

### 4. Using CSS as a Background

```css
.example { background-image: url('image.svg'); }
```

* **Advantages**:
  * Easy to use for background images.
* **Disadvantages**:
  * No interactivity or ability to manipulate SVG content.

### 5. Using the `<iframe>` Tag

```html
<iframe src="image.svg"></iframe>
```

* **Advantages**:
  * Can isolate SVG from the main page, which is useful for security.
* **Disadvantages**:
  * Limited interactivity with SVG, cannot be styled with CSS from the main page.

## Conclusion

Each method of adding SVG to web pages has its advantages and disadvantages, and the choice of method depends on the specific needs of the project, such as interactivity, accessibility to SVG elements, and ease of use. If maximum flexibility is needed, the best choice is to insert SVG directly into HTML. If you just need to display an image, the `<img>` or `<object>` tags will work well.
</details>

<details>
<summary>16. How do you create a form in HTML and ensure its validation?</summary>

Creating a form in HTML and ensuring its validation are important steps when developing web applications. Here's how to do it:

## 1. Creating HTML Forms

Here's a basic example of a form containing different types of input fields:

```html
<form id="myForm">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required><br><br>
  
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required><br><br>
  
  <label for="password">Password:</label>
  <input type="password" id="password" name="password" required minlength="6"><br><br>
  
  <label for="age">Age:</label>
  <input type="number" id="age" name="age" min="18" max="100" required><br><br>
  
  <input type="submit" value="Submit">
</form>
```

## 2. Explanation of Form Fields

* `<form>`: The main tag for creating a form. The `id` attribute can set an identifier for JavaScript or CSS.
* `<label>`: Used to describe input fields. The `for` attribute links the label with the corresponding field.
* `<input>`: Used to create input fields.
   * `type`: Defines the field type (text, email, password, number, etc.).
   * `required`: The field is mandatory to fill out.
   * `minlength`, `min`, `max`: Define minimum/maximum length and numerical limitations.
* `<input type="submit">`: Button to submit the form.

## 3. Form Validation

HTML provides basic form validation using attributes such as `required`, `minlength`, `min`, `max`, `pattern`, etc. However, for more complex checks, JavaScript can be used.

Example of validation with JavaScript:

```html
<script>
  document.getElementById('myForm').addEventListener('submit', function(event) {
    let valid = true;
    
    // Check if name exists
    const name = document.getElementById('name').value;
    if (name.trim() === '') {
      valid = false;
      alert('Name cannot be empty');
    }
    
    // Check if email exists
    const email = document.getElementById('email').value;
    if (!email.includes('@')) {
      valid = false;
      alert('Invalid email');
    }
    
    // If validation fails, cancel form submission
    if (!valid) {
      event.preventDefault();
    }
  });
</script>
```

## 4. Explanation of Validation

* `addEventListener`: Adds an event handler for the form to listen for the `submit` event.
* **Field Verification**: You can perform various checks for each field:
   * For the **name** field, it checks if it's not empty.
   * For the **email** field, it checks if it contains the "@" symbol.
* `event.preventDefault()`: Cancels the browser's default behavior for form submission if validation fails.

## Conclusion

Thus, you can create an HTML form with basic validation using HTML attributes and JavaScript for more detailed checks. This provides a better experience for users, avoiding errors when filling out the form.
</details>

<details>
<summary>17. What are the types of lists in HTML? What are ul / ol / dl?</summary>

In HTML, there are three main types of lists used to organize and structure information:

1. **Ordered Lists (`<ol>`)**  
   Ordered lists are used when the sequence of items matters. Each list item is automatically numbered.

   **Example:**
   ```html
   <ol>
     <li>First</li>
     <li>Second</li>
     <li>Third</li>
   </ol>
   ```
   This will render as:
   - First
   - Second
   - Third

2. **Unordered Lists (`<ul>`)**  
   Unordered lists are used when the sequence of items does not matter. Each item is marked with a bullet by default.

   **Example:**
   ```html
   <ul>
     <li>Apple</li>
     <li>Banana</li>
     <li>Orange</li>
   </ul>
   ```
   This will render as:
   - Apple
   - Banana
   - Orange

3. **Definition Lists (`<dl>`)**  
   Definition lists are used to present terms and their definitions. A definition list consists of terms (`<dt>`) and descriptions (`<dd>`).

   **Example:**
   ```html
   <dl>
     <dt>HTML</dt>
     <dd>A markup language used to create web pages.</dd>

     <dt>CSS</dt>
     <dd>A styling language used to design web pages.</dd>

     <dt>JavaScript</dt>
     <dd>A programming language used to create interactive elements on web pages.</dd>
   </dl>
   ```
   This will render as:
   - **HTML**: A markup language used to create web pages.
   - **CSS**: A styling language used to design web pages.
   - **JavaScript**: A programming language used to create interactive elements on web pages.

**Summary:**
- `<ol>`: Ordered list, where the sequence matters.
- `<ul>`: Unordered list, where the sequence does not matter.
- `<dl>`: Definition list, consisting of terms and their definitions.

These types of lists are fundamental tools in HTML for organizing content, improving readability, and structuring information clearly.

</details>

<details>
<summary>18. What is an iframe and what is it used for?</summary>

An `<iframe>` (inline frame) is an HTML tag that allows embedding one HTML document within another. In other words, it creates a "window" or "frame" through which you can display another web page, video, map, or other content without leaving the main page.

### Key Features and Uses of `<iframe>`:

#### 1. Embedding Content:
`<iframe>` is often used to embed content from other websites, such as YouTube videos, Google Maps, or third-party widgets.

#### 2. Displaying External Output:
It can display images, forms, or PDF documents from other sources.

#### 3. Analytics Dashboards:
Some companies use `<iframe>` to show analytics dashboards that shouldn't interfere with the site's primary navigation.

### Example:
```html
<iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" width="560" height="315" frameborder="0" allowfullscreen></iframe>
```
This embeds a YouTube video into the page.

### Common `<iframe>` Attributes:
- **`src`**: The URL of the document or resource to display in the iframe.
- **`width`** and **`height`**: Define the dimensions of the iframe.
- **`frameborder`**: Controls the visibility of the iframe's border (deprecated in HTML5).
- **`allowfullscreen`**: Allows content (e.g., video) to be viewed in fullscreen mode.

### Pros and Cons:

**Pros:**
- Easy way to embed external content.
- Allows displaying external resources without altering the main page's content.

**Cons:**
- **Security risks**: Potential misuse for malicious purposes like clickjacking.
- **SEO issues**: Content in iframes might not be indexed properly by search engines.

### Conclusion:
The `<iframe>` tag is a powerful tool for embedding external content into web pages, but its use should be carefully managed to ensure security and search engine optimization.

</details>

<details>
<summary>19. What are the methods of submitting form data in HTML?</summary>

In HTML, there are two primary methods for submitting form data:

### 1. GET Method

**Description**: Form data is sent via the URL. All form parameters are appended to the URL as a query string.

**Syntax**:

```html
<form action="url" method="get">
    <!-- form fields -->
</form>
```

**Advantages**:
- Data is visible in the URL, which can be useful for sharing (e.g., filters on pages).
- Suitable for requests that do not alter server data (e.g., search).

**Disadvantages**:
- URL length is limited (depends on the browser, usually around 2000 characters).
- Less secure as sensitive data (e.g., passwords) is exposed in the URL.

---

### 2. POST Method

**Description**: Form data is sent in the body of the HTTP request rather than in the URL.

**Syntax**:

```html
<form action="url" method="post">
    <!-- form fields -->
</form>
```

**Advantages**:
- Can send large amounts of data (no length limit).
- More secure for sensitive data since it is not shown in the URL.
- Typically used for operations that modify server data (e.g., registration, login).

**Disadvantages**:
- Not suitable for bookmarking or sharing, as the data is not in the URL.

---

### Choosing a Method

When choosing between GET and POST, consider the type of data you're sending and the context of its use.  
- Use **GET** for data retrieval (e.g., search queries).  
- Use **POST** for data modification or when sending sensitive information.

</details>

<details>
<summary><strong>20. What are the main differences between block-level and inline elements in HTML? How do they affect page structure?</strong></summary>

In HTML, elements are categorized into two main types: block-level and inline elements. Here's a breakdown of their key differences:

<ol>
  <li>
    <strong>Block-level elements</strong><br />
    <ul>
      <li><strong>Definition:</strong> These elements take up the full width of their container and start on a new line.</li>
      <li><strong>Examples:</strong> <code>&lt;div&gt;</code>, <code>&lt;p&gt;</code>, <code>&lt;h1&gt;</code> to <code>&lt;h6&gt;</code>, <code>&lt;ul&gt;</code>, <code>&lt;ol&gt;</code>, <code>&lt;table&gt;</code>, <code>&lt;section&gt;</code>, <code>&lt;article&gt;</code>, <code>&lt;header&gt;</code>, <code>&lt;footer&gt;</code>, <code>&lt;nav&gt;</code>.</li>
      <li><strong>Impact:</strong> They create structural blocks in the document and can contain other block-level or inline elements. This is useful for organizing complex layouts.</li>
    </ul>
  </li>
  <li>
    <strong>Inline elements</strong><br />
    <ul>
      <li><strong>Definition:</strong> These elements take only as much width as their content requires and do not start on a new line.</li>
      <li><strong>Examples:</strong> <code>&lt;span&gt;</code>, <code>&lt;a&gt;</code>, <code>&lt;img&gt;</code>, <code>&lt;strong&gt;</code>, <code>&lt;em&gt;</code>, <code>&lt;label&gt;</code>, <code>&lt;input&gt;</code>, <code>&lt;button&gt;</code>.</li>
      <li><strong>Impact:</strong> Typically used for styling or embedding interactive parts within text without breaking flow.</li>
    </ul>
  </li>
</ol>

<strong>Summary Table:</strong>

<table>
  <thead>
    <tr>
      <th>Feature</th>
      <th>Block-level Elements</th>
      <th>Inline Elements</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Width</td>
      <td>Full width of the container</td>
      <td>Only as wide as content</td>
    </tr>
    <tr>
      <td>Line Break</td>
      <td>Starts on a new line</td>
      <td>Stays in the same line</td>
    </tr>
    <tr>
      <td>Examples</td>
      <td><code>&lt;div&gt;</code>, <code>&lt;p&gt;</code></td>
      <td><code>&lt;span&gt;</code>, <code>&lt;a&gt;</code></td>
    </tr>
    <tr>
      <td>Purpose</td>
      <td>Structure and layout</td>
      <td>Formatting and interaction</td>
    </tr>
  </tbody>
</table>

<strong>Conclusion:</strong>
Understanding the distinction between block-level and inline elements is crucial for structuring HTML documents effectively and applying CSS for the desired layout and visual behavior.

</details>

<details>
<summary><strong>21. What are CSS selectors? Provide examples.</strong></summary>

CSS selectors are tools that allow styles to be applied to specific HTML elements based on their properties. They define which elements in a document will be styled.

### Basic types of CSS selectors:

**1. Type Selector**  
Applies styles to all elements of a specific type.  
Example:
```css
p {
  color: blue;
}
```
This rule changes the text color of all `<p>` tags to blue.

**2. Class Selector**  
Targets elements with a specific class using a dot (`.`) before the class name.  
Example:
```css
.btn {
  background-color: green;
}
```
This applies styles to all elements with the class `btn`.

**3. ID Selector**  
Targets a specific element with a unique ID using a hash (`#`).  
Example:
```css
#header {
  font-size: 24px;
}
```
This rule changes the font size of the element with ID `header`.

**4. Attribute Selector**  
Selects elements with a specific attribute or attribute value.  
Example:
```css
input[type="text"] {
  border: 1px solid black;
}
```
This styles all `<input>` elements with `type="text"`.

**5. Combinators**

- **Descendant Selector (` `)**: Targets elements that are descendants of another element.  
Example:
```css
div p {
  color: red;
}
```
Styles all `<p>` tags inside a `<div>`.

- **Child Selector (`>`)**: Targets only direct children.  
Example:
```css
ul > li {
  list-style: none;
}
```
Applies styles only to `<li>` elements directly under a `<ul>`.

- **Adjacent Sibling Selector (`+`)**: Styles the element immediately following another.  
Example:
```css
h1 + p {
  margin-top: 0;
}
```
Applies styles to the first `<p>` that comes right after an `<h1>`.

**6. Group Selector**  
Applies the same styles to multiple elements.  
Example:
```css
h1, h2, h3 {
  font-family: Arial, sans-serif;
}
```
This sets the font for `<h1>`, `<h2>`, and `<h3>`.

**Conclusion:**
CSS selectors help efficiently target and style elements on a webpage, enabling you to create structured and visually appealing layouts.

</details>

<details>
<summary><strong>22. How does inheritance work in CSS?</strong></summary>

Inheritance in CSS allows child elements to automatically receive styles from their parent elements. This helps avoid redundant code and simplifies style management.

### Inherited properties:
Some CSS properties are inherited by default. For example, if you set the text color on a parent element, all child elements inherit that color unless otherwise specified.

Example:
```css
body {
  color: blue;
}
```
All text elements inside `<body>` will appear blue because they inherit the color.

**Common inherited properties include:**
- `color`
- `font-family`
- `font-size`
- `line-height`
- `text-align`
- `visibility`

### Non-inherited properties:
Many properties, especially those related to box model and layout, are not inherited by default.

Example:
```css
div {
  margin: 20px;
}
```
The `margin` property will not be inherited by child elements unless explicitly specified.

### Forcing inheritance with `inherit`:
You can force inheritance for a property by using the `inherit` value.

Example:
```css
div {
  border: 2px solid red;
}

p {
  border: inherit; /* Forces the paragraph to inherit the border */
}
```

### Default values:
If a child element does not inherit a property, it falls back to the browser’s default styles for that property.

### Inheritance context:
Inheritance only works within the DOM hierarchy—styles are passed down from parent to child.

Example:
```html
<div class="parent">
  <p class="child">This is a paragraph.</p>
</div>
```
```css
.parent {
  color: green;
  font-size: 18px;
}

.child {
  font-size: inherit; /* Inherits font-size from .parent */
}
```
In this example, the paragraph will be green and have a font size of 18px.

**Conclusion:**  
Inheritance in CSS makes it easier to apply consistent styles and reduce repetition. You can control inheritance using values like `inherit` for greater flexibility.

</details>

<details>
<summary><strong>23. What is the CSS Box Model and how can it be changed?</strong></summary>

The CSS Box Model is a fundamental concept that describes how elements are structured and how their dimensions are calculated on a web page. It consists of four main parts:

### Components of the Box Model:

- **Content**: The area where text and images appear. Its size is defined by the `width` and `height` properties.

- **Padding**: Space between the content and the border. It’s defined by the `padding` property and adds to the total size of the element.

- **Border**: Surrounds the padding (if any) and content. Defined using the `border` property.

- **Margin**: The outermost space that separates the element from others. Set with the `margin` property and does not add to the element's box size.

### Visual Structure:
```
+---------------------------+
|        Margin             |
|  +---------------------+ |
|  |      Border         | |
|  |  +--------------+   | |
|  |  |   Padding    |   | |
|  |  | +----------+ |   | |
|  |  | |  Content | |   | |
|  |  | +----------+ |   | |
|  |  +--------------+   | |
|  +---------------------+ |
+---------------------------+
```

### Default Model: `content-box`
By default, browsers use `box-sizing: content-box`, meaning `width` and `height` apply only to the content area. Padding and borders add to the total size.

Example:
```css
.box {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid black;
}
```
Total width: 200 + 40 (padding) + 10 (border) = **250px**

### Alternate Model: `border-box`
To include padding and border within the declared width and height, use `box-sizing: border-box`.

Example:
```css
.box {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid black;
  box-sizing: border-box;
}
```
Total width remains **200px**, making layouts more predictable.

### Summary of `box-sizing` values:
- `content-box`: (default) width/height = content only
- `border-box`: width/height = content + padding + border

### Benefits of `border-box`:
- Easier layout calculations
- Better control over responsive designs
- Prevents layout shifts due to added padding/border

**Conclusion:**  
The box model defines how elements take up space. Switching to `border-box` simplifies layout management by including padding and borders in the element’s total size.

</details>

<details>
<summary><strong>24. What is the difference between margin and padding?</strong></summary>

The key difference between margin and padding lies in where they create space: **outside** the element (margin) vs **inside** the element (padding).

### 1. Margin (Outer Spacing)
- **Definition**: The space between the element’s border and surrounding elements.
- **Purpose**: Controls spacing **outside** the element, separating it from neighboring elements.
- **Effect**: Does **not** affect the element’s box size.
  
Example:
```css
div {
  margin: 20px;
}
```
This creates 20px of space around the `<div>`, separating it from other elements.

---

### 2. Padding (Inner Spacing)
- **Definition**: The space between the content of the element and its border.
- **Purpose**: Controls spacing **inside** the element, between the content and the edge.
- **Effect**: **Adds** to the element’s size in `content-box` model.

Example:
```css
div {
  padding: 20px;
}
```
This creates 20px of space between the `<div>` content and its border.

---

### Visual Comparison
```
+---------------------------+  ← Margin
|       Border              |
|  +---------------------+  |
|  |     Padding         |  |
|  |  +--------------+   |  |
|  |  |   Content    |   |  | ← Content
|  |  +--------------+   |  |
|  +---------------------+  |
+---------------------------+
```

---

### Summary:
- **Margin**: Outer space, affects spacing between elements.
- **Padding**: Inner space, affects spacing inside an element.

</details>

<details>
<summary><strong>25. What is Flexbox? How to build layouts using Flexbox or Grid, and when to use each?</strong></summary>

### What is Flexbox?
Flexbox (Flexible Box Layout) — це CSS-механізм для побудови одновимірних макетів (в ряд або в колонку). Він дозволяє зручно вирівнювати, розподіляти простір і створювати адаптивні інтерфейси.

### Основні поняття:
- **Flex-контейнер** — елемент з `display: flex`.
- **Flex-елементи** — безпосередні нащадки контейнера.

### Властивості Flexbox:
#### Для контейнера:
- `display: flex` — активує Flexbox.
- `flex-direction` — напрямок елементів (`row`, `column`).
- `justify-content` — вирівнювання по головній осі (`flex-start`, `center`, `space-between`).
- `align-items` — вирівнювання по поперечній осі (`stretch`, `center`, `flex-end`).
- `flex-wrap` — дозволяє переносити елементи (`nowrap`, `wrap`).

#### Для елементів:
- `flex-grow` — як елемент розтягується.
- `flex-shrink` — як елемент стискається.
- `flex-basis` — базовий розмір до розтягування.
- `align-self` — індивідуальне вирівнювання елемента.

### Приклад Flexbox:
```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
.item {
  flex: 1;
}
```
```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

---

### Що таке CSS Grid?
Grid — це двовимірна система верстки, що дозволяє розміщувати елементи по рядках **і** по стовпцях.

### Властивості Grid:
#### Для контейнера:
- `display: grid` — активує Grid.
- `grid-template-columns`, `grid-template-rows` — визначають кількість і розміри стовпців/рядків.
- `gap` — відстань між комірками.
- `justify-items`, `align-items` — вирівнювання в комірках.
- `grid-template-areas` — іменовані області макету.

#### Для елементів:
- `grid-column`, `grid-row` — скільки стовпців/рядків займає елемент.
- `grid-area` — прив’язка до області.

### Приклад Grid:
```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 100px;
  gap: 10px;
}
.item {
  background-color: lightgray;
}
```
```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

---

### Коли що використовувати:
- **Flexbox** — ідеально для **одновимірних макетів** (тільки ряд або тільки стовпець), наприклад: горизонтальне меню, картки в ряд.
- **Grid** — чудово підходить для **двовимірних макетів**, де потрібно одночасно керувати рядками і стовпцями, наприклад: сторінка з боковою панеллю, сітка з товарами.

### Висновок:
- Для простих лінійних розташувань — Flexbox.
- Для складніших сіткових макетів — Grid.

</details>

<details>
<summary><strong>26. What are media queries and how are they used?</strong></summary>

### What are Media Queries?
Media queries are a **CSS feature** used to apply styles based on the characteristics of the device or screen displaying the content.
They’re essential for **responsive design**, helping layouts adapt to different screen sizes like phones, tablets, and desktops.

### Common Media Query Features:
- **Width**: `width`, `min-width`, `max-width`
- **Height**: `height`, `min-height`, `max-height`
- **Orientation**: `portrait`, `landscape`
- **Pixel Density**: `resolution`, `min-resolution`
- **Device Type**: `screen`, `print`, etc.

### Syntax:
```css
@media (condition) {
  /* CSS rules */
}
```

### Example:
```css
/* Base styles for all devices */
body {
  font-size: 16px;
  background-color: white;
}

/* Styles for screens wider than 768px */
@media (min-width: 768px) {
  body {
    font-size: 18px;
    background-color: lightgray;
  }
}

/* Styles for screens wider than 1200px */
@media (min-width: 1200px) {
  body {
    font-size: 20px;
    background-color: darkgray;
  }
}
```

### Use Cases:
- Adjust font sizes or layouts for tablets and desktops
- Hide or show elements based on screen size
- Optimize images and graphics for high-resolution displays
- Provide different designs for portrait vs landscape mode

### Orientation Example:
```css
@media (orientation: landscape) {
  /* styles for landscape mode */
}
```

### Resolution Example:
```css
@media (min-resolution: 300dpi) {
  /* styles for high-density displays */
}
```

### Why Are Media Queries Important?
- Enable responsive design for multiple devices
- Improve user experience across screen sizes
- Reduce need for separate mobile websites
- Make layouts flexible and scalable

</details>

<details>
<summary><strong>27. How can you hide an element using CSS? Do opacity: 0, display: none, and visibility: hidden work the same way?</strong></summary>

There are several ways to hide an element in CSS. Each method behaves differently, especially in terms of layout space and interactivity:

### 1. `display: none;`
- **Removes** the element from the document flow.
- It won’t be visible and won’t take up space.

```css
.hidden-element {
  display: none;
}
```

### 2. `visibility: hidden;`
- Hides the element **but keeps its space** in the layout.
- Other elements won’t shift to fill the space.

```css
.hidden-element {
  visibility: hidden;
}
```

### 3. `opacity: 0;`
- Makes the element **completely transparent**.
- It still takes up space and remains **interactive** (clickable).

```css
.hidden-element {
  opacity: 0;
}
```

### Key Differences:
| Property           | Visible? | Takes Space? | Interactive? |
|--------------------|----------|---------------|----------------|
| `display: none`    | ❌       | ❌            | ❌             |
| `visibility: hidden` | ❌     | ✅            | ❌             |
| `opacity: 0`       | ❌       | ✅            | ✅             |

### When to Use Each:
- Use `display: none` to completely remove an element from the layout.
- Use `visibility: hidden` if you want the space to remain but the element to be hidden.
- Use `opacity: 0` if the element should be hidden but still **respond to events** (like for animations or transitions).

</details>

<details>
<summary><strong>28. How can you center a logo on the screen using CSS?</strong></summary>

Centering a logo on the screen is a common task in web design. There are several CSS techniques to achieve this depending on your needs. Here are the most common methods:

### 1. Using Flexbox:

```html
<div class="container">
  <img src="logo.png" alt="Logo" class="logo">
</div>
```

```css
html, body {
  height: 100%;
  margin: 0;
}

.container {
  display: flex;
  justify-content: center;  /* Horizontal centering */
  align-items: center;      /* Vertical centering */
  height: 100vh;            /* Full viewport height */
}

.logo {
  max-width: 100px;         /* Optional size constraint */
}
```

### 2. Using CSS Grid:

```html
<div class="container">
  <img src="logo.png" alt="Logo" class="logo">
</div>
```

```css
html, body {
  height: 100%;
  margin: 0;
}

.container {
  display: grid;
  place-items: center;      /* Center both horizontally and vertically */
  height: 100vh;
}

.logo {
  max-width: 100px;
}
```

### 3. Using Absolute Positioning:

```html
<div class="container">
  <img src="logo.png" alt="Logo" class="logo">
</div>
```

```css
html, body {
  height: 100%;
  margin: 0;
}

.container {
  position: relative;
  height: 100vh;
}

.logo {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  max-width: 100px;
}
```

### Summary:
- **Flexbox** is the most commonly used and is very readable.
- **Grid** is powerful and great for layouts.
- **Absolute positioning** gives more manual control but can be trickier with responsiveness.

</details>

<details>
<summary><strong>29. How can you center a logo on the screen using CSS?</strong></summary>

Centering a logo on the screen is a common task in web design. There are several CSS techniques to achieve this depending on your needs. Here are the most common methods:

### 1. Using Flexbox:

```html
<div class="container">
  <img src="logo.png" alt="Logo" class="logo">
</div>
```

```css
html, body {
  height: 100%;
  margin: 0;
}

.container {
  display: flex;
  justify-content: center;  /* Horizontal centering */
  align-items: center;      /* Vertical centering */
  height: 100vh;            /* Full viewport height */
}

.logo {
  max-width: 100px;         /* Optional size constraint */
}
```

### 2. Using CSS Grid:

```html
<div class="container">
  <img src="logo.png" alt="Logo" class="logo">
</div>
```

```css
html, body {
  height: 100%;
  margin: 0;
}

.container {
  display: grid;
  place-items: center;      /* Center both horizontally and vertically */
  height: 100vh;
}

.logo {
  max-width: 100px;
}
```

### 3. Using Absolute Positioning:

```html
<div class="container">
  <img src="logo.png" alt="Logo" class="logo">
</div>
```

```css
html, body {
  height: 100%;
  margin: 0;
}

.container {
  position: relative;
  height: 100vh;
}

.logo {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  max-width: 100px;
}
```

### Summary:
- **Flexbox** is the most commonly used and is very readable.
- **Grid** is powerful and great for layouts.
- **Absolute positioning** gives more manual control but can be trickier with responsiveness.

</details>

<details>
<summary><strong>30. How to position a close button (cross) at the top right corner of an element?</strong></summary>

To place a close button (cross) at the top right corner of an element (e.g., a modal window or notification), you can use CSS positioning. Below are two common approaches to implement this:

### 1. Using Absolute Positioning:

```html
<div class="modal">
  <button class="close-button">✖</button>
  <h2>Title</h2>
  <p>Content of the modal window.</p>
</div>
```

```css
.modal {
  position: relative; /* Container for positioning */
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  width: 300px;
}

.close-button {
  position: absolute; /* Absolute positioning */
  top: 10px; /* Distance from the top edge */
  right: 10px; /* Distance from the right edge */
  background: none; /* No background */
  border: none; /* No border */
  font-size: 20px; /* Font size */
  cursor: pointer; /* Pointer cursor on hover */
}
```

### 2. Using Flexbox in the Header:

If you want the close button to always be in the top right corner, you can also use Flexbox:

```html
<div class="modal">
  <div class="header">
    <h2>Title</h2>
    <button class="close-button">✖</button>
  </div>
  <p>Content of the modal window.</p>
</div>
```

```css
.modal {
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  width: 300px;
}

.header {
  display: flex;
  justify-content: space-between; /* Aligns elements to the edges */
  align-items: center; /* Vertically centers */
}

.close-button {
  background: none;
  border: none;
  font-size: 20px;
  cursor: pointer;
}
```

### Which Method to Choose:
- **Absolute Positioning**: Use this if you want precise control over the button's placement, regardless of the content.
- **Flexbox**: Use this if you want flexible positioning where elements in the header (like text and close button) align dynamically.

Both methods will allow you to place the close button in the top right corner of the element.

</details>

