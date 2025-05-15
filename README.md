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

<details>
<summary><strong>31. How to make the last item in a list red regardless of its length without JavaScript?</strong></summary>

Yes, you can use the `:last-child` pseudo-class to style the last item of a list without JavaScript. Here’s how you can do it:

### HTML:
```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
  <li>Item 4</li> <!-- Last item -->
</ul>
```

### CSS:
```css
li:last-child {
  color: red; /* Changes the text color to red for the last list item */
}
```

### Explanation:
- `li:last-child`: This selector targets the last `<li>` element **only if** it is the last child of its parent (in this case, the `<ul>`).
- `color: red;`: This applies a red color to the text of the last list item.

This approach works for any list length—the last item will always be red, no matter how many items you add or remove.
</details>

<details>
<summary><strong>32. What is a pseudo-class and why do we need it?</strong></summary>

A **CSS pseudo-class** is a keyword added to selectors that specifies a special state of the selected elements, without needing to add extra HTML or classes. It lets you style elements based on user interaction or their position in the DOM.

### Common pseudo-classes:

#### `:hover`
Applies styles when the user hovers over an element with a pointer (like a mouse):
```css
a:hover {
  color: blue;
}
```

#### `:focus`
Styles an element when it gains focus (e.g. an input field):
```css
input:focus {
  border: 2px solid green;
}
```

#### `:active`
Applies styles when the element is being activated (e.g. clicked):
```css
button:active {
  background-color: red;
}
```

#### `:first-child` / `:last-child`
Selects the first or last child of a parent element:
```css
li:first-child {
  font-weight: bold;
}
li:last-child {
  color: red;
}
```

#### `:nth-child(n)`
Selects elements based on their position:
```css
li:nth-child(2) {
  color: green;
}
```

### Why use pseudo-classes?
- **State-based styling**: Apply styles on interaction (hover, focus, active).
- **Cleaner HTML**: No need for extra classes or JavaScript.
- **Better UX**: Improve user feedback and accessibility.
- **Flexible targeting**: Style elements based on position or behavior.

</details>

<details>
<summary><strong>33. What are the ways to set color in CSS?</strong></summary>

CSS offers several ways to define colors. Each method provides different levels of precision and flexibility:

### 1. **Color names**
Use predefined color names like `red`, `blue`, `green`, etc.:
```css
color: red;
```
Simple and readable, but limited to a fixed set of names.

### 2. **Hexadecimal notation (Hex)**
Define colors using a `#RRGGBB` or short `#RGB` format:
```css
color: #FF0000; /* Red */
color: #FFF;     /* White (short form) */
```

### 3. **RGB (Red, Green, Blue)**
Specify intensity of red, green, and blue (0–255):
```css
color: rgb(255, 0, 0); /* Red */
```

### 4. **RGBA (RGB + Alpha)**
Same as RGB but includes alpha for opacity (0–1):
```css
color: rgba(255, 0, 0, 0.5); /* Semi-transparent red */
```

### 5. **HSL (Hue, Saturation, Lightness)**
Set color using angle for hue, and percentages for saturation & lightness:
```css
color: hsl(0, 100%, 50%); /* Red */
```

### 6. **HSLA (HSL + Alpha)**
HSL with an alpha channel for transparency:
```css
color: hsla(0, 100%, 50%, 0.5); /* Semi-transparent red */
```

### 7. **CSS Variables (Custom Properties)**
Store color values in variables for reuse:
```css
:root {
  --main-color: #FF0000;
}
element {
  color: var(--main-color);
}
```
Great for consistent theming and easy updates across the project.

</details>

<details>
<summary><strong>34. What is z-index in CSS? Does every element have one?</strong></summary>

### What is `z-index`?

`z-index` is a CSS property that controls the vertical stacking order of elements that overlap. It only applies to elements that have a `position` value other than `static` (e.g., `relative`, `absolute`, `fixed`, or `sticky`).

### How it works:

- Elements with **higher `z-index` values** appear **in front** of elements with lower values.
- If two overlapping elements have the same `z-index` or none is set, the one later in the HTML (DOM) will be on top.

### Example:
```css
.box1 {
  position: absolute;
  z-index: 1;
  background-color: red;
}

.box2 {
  position: absolute;
  z-index: 2;
  background-color: blue;
}
```
In this case, `.box2` will appear above `.box1`.

### Does every element have a `z-index`?

No — only **positioned elements** (with `position` not equal to `static`) can have an effective `z-index`. Non-positioned elements ignore this property.

</details>

<details>
<summary><strong>35. What are the advantages and disadvantages of using CSS preprocessors?</strong></summary>

CSS preprocessors like SASS, LESS, and Stylus extend the capabilities of standard CSS by introducing advanced features and tools.

### ✅ Advantages:

- **Extended capabilities**: variables, nested selectors, mixins, functions, and imports make stylesheet structure more efficient.
- **Modularity**: allows splitting code into manageable, reusable parts.
- **Less duplication**: shared styles can be stored in mixins or variables.
- **Easier maintenance**: cleaner, more readable structure helps with large projects.
- **Functions and calculations**: helpful for dynamic values like spacing or color adjustments.

### ❌ Disadvantages:

- **Learning curve**: requires additional knowledge, especially for beginners.
- **Compilation step**: preprocessors must be compiled into standard CSS, adding complexity to the workflow.
- **Development performance**: large or complex configurations can slow down build times.
- **Overengineering**: misuse of features like excessive nesting can lead to messy code.
- **Tool dependency**: needs specific environments and tools to work properly.

### Conclusion
CSS preprocessors are powerful for large, well-structured projects but may be unnecessary for smaller or simpler tasks.

</details>

<details>
<summary><strong>36. What are the methods of centering elements in CSS?</strong></summary>

Centering elements in CSS depends on the type of element and the layout context. Here are several common methods:

### 1. **Horizontal centering of block elements**

#### a. `margin: auto`
```css
.element {
  width: 50%;
  margin: 0 auto;
}
```

#### b. **Flexbox**
```css
.container {
  display: flex;
  justify-content: center;
}
```

#### c. **Grid**
```css
.container {
  display: grid;
  place-items: center;
}
```

### 2. **Vertical centering of block elements**

#### a. **Flexbox**
```css
.container {
  display: flex;
  align-items: center;
  height: 100vh;
}
```

#### b. **Grid**
```css
.container {
  display: grid;
  height: 100vh;
  place-items: center;
}
```

#### c. **Absolute positioning**
```css
.container {
  position: relative;
  height: 100vh;
}

.element {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

### 3. **Centering inline elements (text, inline-block)**

#### a. **Text alignment**
```css
.container {
  text-align: center;
}
```

### 4. **Table display methods**
```css
.container {
  display: table;
  height: 100vh;
  width: 100%;
}

.element {
  display: table-cell;
  vertical-align: middle;
  text-align: center;
}
```

### Conclusion
CSS offers multiple methods for centering elements. Flexbox and Grid are the most versatile and modern solutions, but legacy methods like `margin: auto` or table display can still be useful depending on the situation.

</details>

<details>
<summary><strong>37. What methods of vertical centering in CSS do you know?</strong></summary>

Vertical centering in CSS can be achieved in several ways depending on the layout and context.

### 1. **Flexbox**
```css
.container {
  display: flex;
  align-items: center; /* vertical alignment */
  height: 100vh;
}
```

### 2. **Grid**
```css
.container {
  display: grid;
  height: 100vh;
  place-items: center; /* horizontal + vertical centering */
}
```

### 3. **Absolute positioning with transform**
```css
.container {
  position: relative;
  height: 100vh;
}

.element {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}
```

For full center (both axes):
```css
.element {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

### 4. **Table display method**
```css
.container {
  display: table;
  height: 100vh;
  width: 100%;
}

.element {
  display: table-cell;
  vertical-align: middle;
  text-align: center;
}
```

### 5. **line-height (for single-line text only)**
```css
.element {
  height: 100px;
  line-height: 100px;
  text-align: center;
}
```

### 6. **margin-top (requires fixed height)**
```css
.element {
  height: 100px;
  margin-top: calc((100vh - 100px) / 2);
}
```

### Conclusion
The most modern and flexible solutions for vertical centering are Flexbox and Grid. They are recommended for most use cases. Other methods may be helpful in specific situations or for supporting older browsers.

</details>

<details>
<summary><strong>38. Why do heading levels exist if we can set the size with CSS?</strong></summary>

Although CSS allows full control over the visual appearance of text, HTML heading elements (`<h1>` to `<h6>`) serve purposes that go far beyond styling.

### 1. **Semantic Meaning**
Heading tags define the structure and hierarchy of your content. `<h1>` represents the main heading of a page, followed by `<h2>`, `<h3>`, etc., which introduce sub-sections. This hierarchy helps both users and machines understand the logical flow of the content.

### 2. **Search Engine Optimization (SEO)**
Search engines use heading tags to interpret the organization and importance of different parts of your content. Proper use of headings—especially a single, relevant `<h1>`—can improve how a page is indexed and ranked.

### 3. **Accessibility**
Screen readers rely on headings to help users with visual impairments navigate a page efficiently. Proper heading levels allow users to skip to specific sections, enhancing the overall user experience for assistive technologies.

### 4. **Content Organization**
Even for sighted users, consistent use of heading levels makes it easier to scan and digest content. Readers can quickly identify the main topics and subtopics.

### 5. **Maintainable Styling**
Using semantic tags allows you to style all headings of a specific level via CSS selectors (`h2`, `h3`, etc.) rather than assigning classes or inline styles to every heading. This keeps your code cleaner and easier to maintain.

### Conclusion
Heading levels are an essential part of writing meaningful and accessible HTML. They help structure content, support SEO, improve accessibility, and make styling more manageable. So while CSS can control how a heading looks, the tags themselves carry important structural value.

</details>

<details>
  <summary><strong>39. What are the positioning options for an element in CSS?</strong></summary>

  CSS provides several ways to position elements on a page. Each method serves different purposes depending on the layout needs:

  **1. Static Positioning**  
  - **Description:** Default positioning. Elements appear in the normal document flow and cannot be offset using `top`, `right`, `bottom`, or `left`.  
  - **Use Case:** Suitable for elements that do not require special positioning.

  **2. Relative Positioning**  
  - **Description:** The element is positioned relative to its normal position. You can adjust its location using `top`, `right`, `bottom`, or `left`.  
  - **Use Case:** Commonly used to establish a positioning context for absolutely positioned children.

  **3. Absolute Positioning**  
  - **Description:** The element is removed from the document flow and positioned relative to the nearest positioned ancestor (`relative`, `absolute`, or `fixed`). If none is found, it uses the document root.  
  - **Use Case:** Ideal for precise placement without affecting surrounding elements.

  **4. Fixed Positioning**  
  - **Description:** The element is positioned relative to the browser window and stays fixed during scrolling.  
  - **Use Case:** Useful for headers, footers, or "back to top" buttons that stay visible while scrolling.

  **5. Sticky Positioning**  
  - **Description:** The element behaves like `relative` until a certain scroll threshold is met, then switches to `fixed`.  
  - **Use Case:** Used for sticky headers or navigation bars that stick when scrolling reaches a defined point.

  **Conclusion**  
  Understanding each positioning method allows you to structure layouts effectively and meet design goals in responsive and dynamic web interfaces.

</details>

<details>
  <summary><strong>40. What are the different types of <code>display</code> in CSS? Which one do you use most often? What is special about <code>inline-block</code>?</strong>strong></summary>

  The <code>display</code> property in CSS defines how an element is displayed on the web page. Below are the main types:

  **1. block**  
  - **Description:** The element takes up the full width available and starts on a new line.  
  - **Examples:** &lt;div&gt;, &lt;p&gt;, &lt;h1&gt;, &lt;ul&gt;, &lt;li&gt;

  **2. inline**  
  - **Description:** The element only takes as much width as its content requires and does not start on a new line.  
  - **Examples:** &lt;span&gt;, &lt;a&gt;, &lt;strong&gt;

  **3. inline-block**  
  - **Description:** Behaves like an inline element but allows setting width and height like a block element.  
  - **Use Case:** Ideal for placing elements side by side with full control over their dimensions and spacing.

  **4. none**  
  - **Description:** The element is not displayed and does not take up any space in the layout.  
  - **Use Case:** Useful for hiding elements without removing them from the DOM.

  **5. flex**  
  - **Description:** Creates a flexible container to align and distribute space among items, either in a row or column.

  **6. grid**  
  - **Description:** Creates a grid-based layout system that supports two-dimensional alignment (both rows and columns).

  **Most Commonly Used:**  
  <code>block</code> and <code>inline</code> are foundational for structuring content, but <code>inline-block</code> is frequently used when you want inline placement with block-level control.

  **Special Feature of <code>inline-block</code>:**  
  Elements with <code>display: inline-block</code> can appear side by side like inline elements, yet allow width, height, margin, and padding to be applied like block elements. This makes it very useful for layouts such as navigation menus or buttons.

  **Conclusion:**  
  Understanding how different <code>display</code> values behave helps in crafting layouts that are flexible, readable, and responsive.

</details>

<details>
  <summary><strong>41. What are the examples of inline-block elements?</strong></summary>
  <p>Here are examples of block, inline, and inline-block elements in HTML:</p>

  <strong>Block elements (block):</strong>
  <ul>
    <li>&lt;div&gt; - Container for other elements.</li>
    <li>&lt;h1&gt; - First-level header.</li>
    <li>&lt;h2&gt; - Second-level header.</li>
    <li>&lt;h3&gt; - Third-level header.</li>
    <li>&lt;h4&gt; - Fourth-level header.</li>
    <li>&lt;h5&gt; - Fifth-level header.</li>
    <li>&lt;h6&gt; - Sixth-level header.</li>
    <li>&lt;p&gt; - Paragraph of text.</li>
    <li>&lt;ul&gt; - Unordered list.</li>
    <li>&lt;ol&gt; - Ordered list.</li>
    <li>&lt;li&gt; - List item.</li>
    <li>&lt;blockquote&gt; - Block quote.</li>
    <li>&lt;header&gt; - Document or section header.</li>
    <li>&lt;footer&gt; - Document or section footer.</li>
    <li>&lt;section&gt; - Document section.</li>
    <li>&lt;article&gt; - Self-contained content that can be distributed separately.</li>
    <li>&lt;nav&gt; - Navigation links.</li>
    <li>&lt;figure&gt; - Figure for image or illustration.</li>
    <li>&lt;figcaption&gt; - Caption for the &lt;figure&gt; element.</li>
    <li>&lt;main&gt; - Main content of the document.</li>
  </ul>

  <strong>Inline elements (inline):</strong>
  <ul>
    <li>&lt;span&gt; - Inline container for text.</li>
    <li>&lt;a&gt; - Hyperlink.</li>
    <li>&lt;strong&gt; - Strong emphasis (bold).</li>
    <li>&lt;em&gt; - Emphasized text (italic).</li>
    <li>&lt;b&gt; - Bold text.</li>
    <li>&lt;i&gt; - Italic text.</li>
    <li>&lt;small&gt; - Smaller text.</li>
    <li>&lt;sub&gt; - Subscript text.</li>
    <li>&lt;sup&gt; - Superscript text.</li>
    <li>&lt;code&gt; - Program code.</li>
    <li>&lt;img&gt; - Image.</li>
    <li>&lt;br&gt; - Line break.</li>
    <li>&lt;hr&gt; - Horizontal line.</li>
    <li>&lt;time&gt; - Time element.</li>
    <li>&lt;cite&gt; - Citation element.</li>
    <li>&lt;q&gt; - Inline quotation.</li>
  </ul>

  <strong>Inline-block elements (inline-block):</strong>
  <ul>
    <li>&lt;button&gt; - Button.</li>
    <li>&lt;input&gt; - Input field.</li>
    <li>&lt;label&gt; - Label for a form element.</li>
    <li>&lt;select&gt; - Dropdown list.</li>
  </ul>
</details>

<details>
  <summary><strong>42. What are pseudo-classes and pseudo-elements? What is the difference between them? How do you use them in CSS?</strong></summary>

  <p><strong>Pseudo-classes</strong> and <strong>pseudo-elements</strong> are concepts in CSS that allow you to style elements based on their state or structure without changing the HTML.</p>

  <strong>Pseudo-classes</strong>
  <ul>
    <li><strong>What they are:</strong> Used to style elements based on their state or position in the document. They begin with a single colon (<code>:</code>).</li>
    <li><strong>Examples:</strong>
      <ul>
        <li><code>:hover</code> — styles an element when the user hovers over it.</li>
        <li><code>:focus</code> — styles an element when it gains focus.</li>
        <li><code>:nth-child(n)</code> — targets elements based on their position in the parent.</li>
      </ul>
    </li>
    <li><strong>Usage Example:</strong></li>
  </ul>

  <pre><code>button:hover {
  background-color: blue;
}

input:focus {
  border: 2px solid green;
}

li:nth-child(odd) {
  background-color: lightgray;
}</code></pre>

  <strong>Pseudo-elements</strong>
  <ul>
    <li><strong>What they are:</strong> Used to style specific parts of an element. In CSS3, they use a double colon (<code>::</code>), although some browsers still support the single-colon syntax.</li>
    <li><strong>Examples:</strong>
      <ul>
        <li><code>::before</code> — inserts content before the element.</li>
        <li><code>::after</code> — inserts content after the element.</li>
        <li><code>::first-line</code> — styles the first line of text.</li>
        <li><code>::first-letter</code> — styles the first letter of text.</li>
      </ul>
    </li>
    <li><strong>Usage Example:</strong></li>
  </ul>

  <pre><code>p::before {
  content: "Note: ";
  font-weight: bold;
}

h1::first-line {
  color: red;
}

blockquote::after {
  content: " - Author";
}</code></pre>

  <strong>Key Differences:</strong>
  <ul>
    <li><strong>Function:</strong> Pseudo-classes select elements based on state or position; pseudo-elements style parts of an element.</li>
    <li><strong>Syntax:</strong> Pseudo-classes use <code>:</code>, pseudo-elements use <code>::</code> in CSS3.</li>
  </ul>

  <p><strong>Conclusion:</strong> Both pseudo-classes and pseudo-elements are powerful tools in CSS that enhance styling capabilities without requiring changes to the HTML structure.</p>
</details>

<details>
  <summary><strong>43. What is responsive (adaptive) design?</strong></summary>

  <p><strong>Responsive (adaptive) design</strong> is a web design approach that ensures optimal viewing and interaction experience across a wide range of devices, including desktops, tablets, and smartphones. The goal is to create layouts that automatically adjust to different screen sizes and usage conditions.</p>

  <strong>Key principles of responsive design:</strong>

  <ul>
    <li><strong>Flexible layouts:</strong> Use relative units like <code>%</code>, <code>vw</code>, and <code>vh</code> instead of fixed units like <code>px</code> to allow elements to scale properly across different screen sizes.</li>
    <li><strong>Media queries:</strong> Apply CSS styles based on device characteristics such as width, height, and orientation to adapt layout and content accordingly.</li>
    <li><strong>Flexible images:</strong> Use images that scale within their container (e.g., using <code>max-width: 100%</code>) to prevent overflow or distortion.</li>
    <li><strong>Touch-friendly elements:</strong> Design buttons and inputs with appropriate size and spacing for touch interaction on mobile devices.</li>
  </ul>

  <strong>Benefits of responsive design:</strong>
  <ul>
    <li><strong>Improved user experience:</strong> Visitors can easily navigate and read content on any device.</li>
    <li><strong>Reduced bounce rate:</strong> Accessible and user-friendly interfaces keep users engaged.</li>
    <li><strong>Single website for all devices:</strong> Eliminates the need to build and maintain separate desktop and mobile versions of a site.</li>
  </ul>

  <p><strong>Conclusion:</strong> Responsive design is essential for modern web development. It ensures accessibility, usability, and performance across diverse devices, increasing user satisfaction and engagement.</p>
</details>

<details>
  <summary><strong>44. What is the difference between images added via the HTML <code>&lt;img&gt;</code> tag and the CSS <code>background-image</code> property?</strong></summary>

  <p><strong>The main difference</strong> lies in their purpose, semantics, and usage:</p>

  <strong>1. Purpose:</strong>
  <ul>
    <li><strong><code>&lt;img&gt;</code> tag:</strong> Used for displaying content images (e.g., photos, logos, illustrations). It's semantic and intended to convey meaningful visual content.</li>
    <li><strong><code>background-image</code>:</strong> Used for decorative or stylistic backgrounds, not core content.</li>
  </ul>

  <strong>2. Semantics:</strong>
  <ul>
    <li><strong><code>&lt;img&gt;</code>:</strong> Provides semantic value and supports the <code>alt</code> attribute, which is useful for accessibility and SEO.</li>
    <li><strong><code>background-image</code>:</strong> Carries no semantic meaning, is not indexed by search engines, and is not accessible to screen readers.</li>
  </ul>

  <strong>3. Styling and positioning:</strong>
  <ul>
    <li><strong><code>&lt;img&gt;</code>:</strong> Can be styled using CSS (e.g., <code>width</code>, <code>height</code>), but has limited flexibility for complex visual effects without extra CSS.</li>
    <li><strong><code>background-image</code>:</strong> Offers full control via CSS properties like <code>background-size</code>, <code>background-repeat</code>, <code>background-position</code>, and supports multiple backgrounds.</li>
  </ul>

  <strong>4. Accessibility and SEO:</strong>
  <ul>
    <li><strong><code>&lt;img&gt;</code>:</strong> Supports accessibility via <code>alt</code> and contributes to SEO.</li>
    <li><strong><code>background-image</code>:</strong> Not accessible and ignored by search engines.</li>
  </ul>

  <p><strong>Conclusion:</strong> Use <code>&lt;img&gt;</code> for meaningful content images. Use <code>background-image</code> for decorative or stylistic purposes only.</p>
</details>


<details>
  <summary><strong>45. How do you handle cross-browser compatibility issues in web development, especially across different browser versions?</strong></summary>

  <p><strong>Ensuring cross-browser compatibility</strong> is an essential part of web development. Here are the strategies I use to address these issues:</p>

  <strong>1. Follow HTML/CSS Standards:</strong>
  <ul>
    <li>I adhere to W3C standards to ensure consistency, as modern browsers strive to support these specifications.</li>
  </ul>

  <strong>2. Test in Multiple Browsers:</strong>
  <ul>
    <li>I regularly test websites on major browsers (Chrome, Firefox, Safari, Edge) and across operating systems (Windows, macOS, iOS, Android) to identify and resolve inconsistencies early.</li>
  </ul>

  <strong>3. Use CSS Reset or Normalize.css:</strong>
  <ul>
    <li>I apply a CSS reset or use Normalize.css to reduce default style inconsistencies across browsers.</li>
  </ul>

  <strong>4. Be Cautious with New Features:</strong>
  <ul>
    <li>I avoid using experimental CSS or JavaScript features unless I’ve verified browser support using tools like <a href="https://caniuse.com" target="_blank">Can I use</a>.</li>
  </ul>

  <strong>5. Use Polyfills and Transpilers:</strong>
  <ul>
    <li>I use polyfills and tools like Babel to provide backward compatibility for newer JavaScript features in older browsers.</li>
  </ul>

  <strong>6. Apply CSS Methodologies:</strong>
  <ul>
    <li>Using structured methodologies like BEM helps maintain consistent styling across browsers and simplifies debugging.</li>
  </ul>

  <strong>7. Add Browser-Specific Styles When Needed:</strong>
  <ul>
    <li>I use vendor prefixes (e.g., <code>-webkit-</code>, <code>-moz-</code>, <code>-ms-</code>) and, if necessary, conditional comments for legacy support (like in Internet Explorer).</li>
  </ul>

  <strong>8. Implement Responsive Design:</strong>
  <ul>
    <li>I use responsive layouts and media queries to ensure proper display on a variety of screen sizes and devices.</li>
  </ul>

  <strong>9. Monitor After Deployment:</strong>
  <ul>
    <li>After launch, I collect user feedback and monitor analytics to catch any browser-specific rendering issues that may still appear.</li>
  </ul>

  <p><strong>Conclusion:</strong> Maintaining cross-browser compatibility requires a proactive and consistent approach throughout development, testing, and post-launch monitoring.</p>
</details>

<details>
  <summary><strong>46. How can HTML and CSS be used to ensure website accessibility?</strong></summary>

  <p>Ensuring accessibility means making a website usable for all users, including those with disabilities. Below are essential practices using HTML and CSS to improve accessibility:</p>

  <strong>1. Use semantic HTML</strong>
  <ul>
    <li>Tags like <code>&lt;header&gt;</code>, <code>&lt;nav&gt;</code>, <code>&lt;main&gt;</code>, <code>&lt;article&gt;</code>, <code>&lt;section&gt;</code>, and <code>&lt;footer&gt;</code> help screen readers understand page structure.</li>
  </ul>

  <strong>2. Add accessibility attributes</strong>
  <ul>
    <li>Use <code>alt</code> attributes on images to describe their content.</li>
    <li>Apply <code>aria-*</code> attributes to provide extra information where necessary (e.g., <code>aria-label</code>, <code>aria-hidden</code>).</li>
  </ul>

  <strong>3. Maintain proper heading structure</strong>
  <ul>
    <li>Use headings (<code>&lt;h1&gt;</code> through <code>&lt;h6&gt;</code>) in a logical order to reflect the content hierarchy.</li>
  </ul>

  <strong>4. Make forms accessible</strong>
  <ul>
    <li>Label every input with a corresponding <code>&lt;label&gt;</code>.</li>
    <li>Use <code>required</code>, <code>aria-required</code>, and <code>aria-invalid</code> to indicate field requirements and validation.</li>
  </ul>

  <strong>5. Ensure sufficient color contrast</strong>
  <ul>
    <li>Text should contrast well with its background to remain readable for users with visual impairments.</li>
    <li>Use online tools (like the WebAIM Contrast Checker) to validate contrast ratios.</li>
  </ul>

  <strong>6. Use CSS wisely for accessibility</strong>
  <ul>
    <li>Avoid using <code>display: none</code> for important content that should be accessible via screen readers.</li>
    <li>Don’t rely solely on color to convey information—add visual cues like underlines or icons.</li>
  </ul>

  <strong>7. Test accessibility</strong>
  <ul>
    <li>Use screen readers and tools like Axe, Lighthouse, or WAVE to test how accessible your site is.</li>
  </ul>

  <strong>8. Enable keyboard navigation</strong>
  <ul>
    <li>All interactive elements should be accessible via the keyboard.</li>
    <li>Use <code>:focus</code> styles and <code>tabindex</code> where appropriate to manage focus states.</li>
  </ul>

  <strong>Conclusion:</strong>
  <p>Accessibility is an ongoing process. By using semantic HTML, structuring content properly, testing frequently, and applying thoughtful CSS, you help make the web inclusive for all users.</p>
</details>

<details>
  <summary><strong>47. How can you implement responsive design using CSS?</strong></summary>

  <p>Responsive design ensures that a website looks and works well on devices of various screen sizes. CSS provides several tools and techniques to achieve this:</p>

  <strong>1. Media Queries</strong>
  <p>Media queries allow you to apply different styles depending on the screen's characteristics, like width, height, or orientation.</p>

  <pre><code>/* Base styles for mobile devices */
body {
  font-size: 16px;
  padding: 10px;
}

/* Styles for tablets */
@media (min-width: 768px) {
  body {
    font-size: 18px;
    padding: 20px;
  }
}

/* Styles for desktops */
@media (min-width: 1024px) {
  body {
    font-size: 20px;
    padding: 30px;
  }
}
</code></pre>

  <strong>2. Fluid Grids</strong>
  <p>Use percentage-based widths instead of fixed pixels so that containers adapt to screen size.</p>

  <pre><code>.container {
  width: 80%;
  max-width: 1200px;
}
</code></pre>

  <strong>3. Responsive Images</strong>
  <p>Ensure images scale correctly within their containers.</p>

  <pre><code>img {
  max-width: 100%;
  height: auto;
}
</code></pre>

  <strong>4. Flexbox and CSS Grid</strong>
  <p>These layout models allow you to build flexible and adaptive layouts easily.</p>

  <strong>Flexbox:</strong>
  <pre><code>.container {
  display: flex;
  flex-wrap: wrap;
}

.item {
  flex: 1 1 200px;
}
</code></pre>

  <strong>CSS Grid:</strong>
  <pre><code>.container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 10px;
}
</code></pre>

  <strong>5. Scalable Text</strong>
  <p>Use relative units (like <code>em</code> or <code>rem</code>) for font sizes to make text scale appropriately.</p>

  <pre><code>body {
  font-size: 1rem;
}

h1 {
  font-size: 2rem;
}
</code></pre>

  <strong>6. Touchable UI Elements</strong>
  <p>Ensure that buttons and interactive elements are large enough for users to tap on touchscreens.</p>

  <pre><code>.button {
  padding: 12px 20px;
  font-size: 16px;
}
</code></pre>

  <strong>Conclusion:</strong>
  <p>By combining media queries, flexible layouts, responsive images, scalable text, and touch-friendly controls, you can create modern, accessible websites that work seamlessly across all devices.</p>
</details>

<details>
  <summary><strong>48. Explain the concept of CSS variables.</strong></summary>

  <p>CSS variables, also known as <strong>custom properties</strong>, allow you to store values in variables and reuse them throughout your CSS. They improve code maintainability, consistency, and flexibility.</p>

  <strong>1. Syntax</strong>
  <p>CSS variables are defined with a <code>--</code> prefix and are typically declared inside the <code>:root</code> selector to make them globally accessible:</p>

  <pre><code>:root {
  --main-color: #3498db;
  --padding: 16px;
}
</code></pre>

  <strong>2. Usage</strong>
  <p>To use a variable, apply the <code>var()</code> function:</p>

  <pre><code>.button {
  background-color: var(--main-color);
  padding: var(--padding);
}
</code></pre>

  <strong>3. Scope</strong>
  <p>CSS variables are scoped, meaning you can override them locally within specific selectors:</p>

  <pre><code>.button {
  --main-color: #e74c3c;
  background-color: var(--main-color);
}
</code></pre>

  <strong>4. Dynamic Updates with JavaScript</strong>
  <p>You can update CSS variables dynamically via JavaScript, allowing for real-time style changes:</p>

  <pre><code>document.documentElement.style.setProperty('--main-color', '#2ecc71');
</code></pre>

  <strong>5. Benefits</strong>
  <ul>
    <li><strong>Maintainability:</strong> Easily update repeated values from one place.</li>
    <li><strong>Flexibility:</strong> Override variables for specific contexts (e.g., media queries or components).</li>
    <li><strong>Less duplication:</strong> Keeps your code DRY and consistent.</li>
  </ul>

  <strong>6. Example</strong>
  <pre><code>:root {
  --font-size: 16px;
  --line-height: 1.5;
}

p {
  font-size: var(--font-size);
  line-height: var(--line-height);
}

.large-text {
  font-size: calc(var(--font-size) * 1.5);
}
</code></pre>

  <strong>Conclusion:</strong>
  <p>CSS variables are a powerful tool for creating scalable and consistent stylesheets. They simplify customization and help manage design tokens across projects.</p>
</details>

<details>
  <summary><strong>49. What typically causes the biggest drops in website performance?</strong></summary>

  <strong>1. Large Images and Media Files</strong><br>
  Uncompressed or incorrectly formatted images (e.g., PNG instead of JPEG) slow down loading. Lack of lazy loading leads to all images being fetched at once.

  <strong>2. Heavy or Complex CSS and JavaScript</strong><br>
  Unoptimized CSS/JS files, unused code, large libraries, and lack of async/defer attributes block rendering.

  <strong>3. Too Many HTTP Requests</strong><br>
  Each asset (image, script, style) triggers a request. No caching increases load times due to repeated fetching.

  <strong>4. Unoptimized Fonts</strong><br>
  Too many font weights or styles increase load size. FOIT (Flash of Invisible Text) delays text rendering.

  <strong>5. Slow Server or No CDN</strong><br>
  A weak or distant server adds latency. Without a CDN, users far from the host receive slower content delivery.

  <strong>6. Large or Deep DOM</strong><br>
  Overly complex or deeply nested HTML structures slow down style and script execution.

  <strong>7. No CSS/JS Optimization</strong><br>
  Lack of minification and file bundling leads to larger payloads and more HTTP requests.

  <strong>8. Rendering Issues</strong><br>
  Styles or scripts that trigger reflows or repaints during interaction hurt performance.

  <strong>9. Poor Mobile Optimization</strong><br>
  Lack of responsive design or unnecessary resource loading on mobile slows the site.

  <strong>10. Slow Database or Inefficient Queries</strong><br>
  Poorly optimized server queries or missing indexes delay dynamic content loading.

  <strong>11. Cross-Browser Compatibility Issues</strong><br>
  Inconsistent rendering between browsers may lead to extra code and degraded performance.

  <strong>Optimization Tips:</strong>
  <ul>
    <li>Compress images (e.g., WebP format).</li>
    <li>Use lazy loading for media.</li>
    <li>Minify and bundle CSS/JS files.</li>
    <li>Enable caching and use a CDN.</li>
    <li>Simplify DOM structure and layout.</li>
    <li>Ensure responsive design for mobile devices.</li>
  </ul>

  <strong>Conclusion:</strong><br>
  Addressing these issues helps improve website load speed, responsiveness, and user experience.
</details>

<details>
  <summary><strong>50. How to make two columns in CSS where one stretches and the other does not?</strong></summary>

  <strong>Using Flexbox:</strong>
  <pre><code>.container {
  display: flex;
}

.fixed-column {
  width: 200px;
  background-color: lightgray;
}

.flex-column {
  flex-grow: 1;
  background-color: lightblue;
}</code></pre>

  <strong>HTML:</strong>
  <pre><code>&lt;div class="container"&gt;
  &lt;div class="fixed-column"&gt;Fixed Column&lt;/div&gt;
  &lt;div class="flex-column"&gt;Flexible Column&lt;/div&gt;
&lt;/div&gt;</code></pre>

  <strong>Explanation:</strong>
  The container becomes a flex container. The first column has a fixed width, while the second uses <code>flex-grow: 1</code> to occupy all available space.

  <strong>Using CSS Grid:</strong>
  <pre><code>.container {
  display: grid;
  grid-template-columns: 200px 1fr;
}

.fixed-column {
  background-color: lightgray;
}

.flex-column {
  background-color: lightblue;
}</code></pre>

  <strong>HTML:</strong>
  <pre><code>&lt;div class="container"&gt;
  &lt;div class="fixed-column"&gt;Fixed Column&lt;/div&gt;
  &lt;div class="flex-column"&gt;Flexible Column&lt;/div&gt;
&lt;/div&gt;</code></pre>

  <strong>Explanation:</strong>
  <code>grid-template-columns: 200px 1fr</code> defines two columns: one fixed at 200px, and the second stretches to fill remaining space using fractional units.

  <strong>Summary:</strong>
  Both Flexbox and Grid work well. Flexbox is great for simple horizontal/vertical layouts. Grid offers more control for complex and two-dimensional designs.
</details>

<details>
  <summary><strong>51. What are the advantages and disadvantages of CSS animations compared to JavaScript animations?</strong></summary>

  <strong>Advantages of CSS animations:</strong>
  <ul>
    <li><strong>Simplicity and ease of use:</strong> CSS animations are easy to write and do not require JavaScript. They are ideal for simple transitions like color, size, or position changes.</li>
    <li><strong>Better performance:</strong> CSS animations are usually more performant as they are processed by the browser using hardware acceleration, especially for properties like <code>transform</code> and <code>opacity</code>.</li>
    <li><strong>Less code and cleaner syntax:</strong> Using <code>@keyframes</code> and <code>transition</code> makes it easy to define animation sequences without complex logic.</li>
    <li><strong>Lower resource usage:</strong> They consume fewer resources and are less CPU-intensive since they are handled by the browser’s rendering engine.</li>
  </ul>

  <strong>Disadvantages of CSS animations:</strong>
  <ul>
    <li><strong>Limited control:</strong> CSS animations lack the flexibility to handle complex logic or conditional animation flows.</li>
    <li><strong>Restricted functionality:</strong> Only certain properties can be animated. Advanced effects like scroll-based or event-driven animations require JavaScript.</li>
    <li><strong>Poor synchronization with events:</strong> It's harder to sync with other actions or execute follow-up logic at the end of an animation.</li>
    <li><strong>Difficult to manage complex animations:</strong> Multi-stage or conditional animations become hard to implement and maintain using just CSS.</li>
  </ul>

  <strong>Advantages of JavaScript animations:</strong>
  <ul>
    <li><strong>Flexibility and interactivity:</strong> JavaScript supports dynamic, user-driven animations with conditions, loops, and real-time updates.</li>
    <li><strong>Full control:</strong> Every aspect of an animation (timing, delay, steps) can be managed programmatically. Animations can be paused, reversed, or modified on the fly.</li>
    <li><strong>Rich ecosystem:</strong> Libraries like GSAP and Anime.js simplify complex animation workflows and offer extensive features.</li>
  </ul>

  <strong>Disadvantages of JavaScript animations:</strong>
  <ul>
    <li><strong>Higher performance cost:</strong> JavaScript animations run on the main thread and may slow down the UI, especially if not optimized.</li>
    <li><strong>More complex to write:</strong> They often require more code and logic, making them harder to implement and maintain than CSS-based approaches.</li>
    <li><strong>No hardware acceleration for some properties:</strong> Unlike CSS, certain animated properties might not benefit from GPU acceleration.</li>
  </ul>

  <strong>Conclusion:</strong><br />
  CSS animations are best for simple, efficient transitions without interaction logic. JavaScript is preferable for advanced, user-driven, or condition-based animations.
</details>

<details>
  <summary><strong>52. How can you override <code>!important</code> or achieve a similar effect without using <code>!important</code>?</strong></summary>

  <strong>Overriding <code>!important</code> is difficult</strong> because it has the highest priority in CSS. However, there are several methods to achieve a similar result:

  <strong>1. Increase selector specificity:</strong><br />
  Use more specific selectors (e.g., adding a parent or ID) to give your rule higher priority than the one using <code>!important</code>.
  <pre><code>/* Original style with !important */
.button {
  color: red !important;
}

/* Override with higher specificity */
.container .button {
  color: blue;
}</code></pre>

  <strong>2. Use inline styles:</strong><br />
  Adding a <code>style</code> attribute directly in HTML gives the rule higher priority than most stylesheet rules.
  <pre><code>&lt;button style="color: green;"&gt;Click Me&lt;/button&gt;</code></pre>

  <strong>3. Use JavaScript to apply inline styles:</strong><br />
  JavaScript can dynamically set styles with <code>!important</code>, overriding existing rules.
  <pre><code>document.getElementById('myButton').style.setProperty('color', 'blue', 'important');</code></pre>

  <strong>4. Place your rule later in the stylesheet:</strong><br />
  If specificity is the same, rules defined later in the stylesheet can override earlier ones — although this doesn't always beat <code>!important</code>.
  <pre><code>.button {
  color: red !important;
}

/* Later rule */
.button {
  color: blue;
}</code></pre>

  <strong>5. Use JavaScript to add/remove classes:</strong><br />
  Dynamically modifying the class list of an element can help apply styles conditionally.
  <pre><code>document.getElementById('myButton').classList.add('override');</code></pre>

  <strong>Conclusion:</strong><br />
  The most reliable ways to override <code>!important</code> are increasing selector specificity and using inline styles. It's best to use <code>!important</code> sparingly to keep styles maintainable.
</details>

<details>
  <summary><strong>53. How can you determine the level of specificity if your new selector is supposed to be more specific?</strong></summary>

  <strong>CSS specificity</strong> is a measurement of how specific a selector is, which determines which rule takes precedence when multiple rules target the same element. Specificity is calculated using four components:

  <ul>
    <li><strong>a</strong>: Inline styles (always 1 if present)</li>
    <li><strong>b</strong>: Number of ID selectors</li>
    <li><strong>c</strong>: Number of class selectors, attribute selectors, and pseudo-classes</li>
    <li><strong>d</strong>: Number of element selectors and pseudo-elements</li>
  </ul>

  The higher the value starting from the left, the more specific the selector.

  <strong>Examples:</strong>

  <pre><code>&lt;div style="color: red;"&gt;Hello&lt;/div&gt;
Specificity: [1, 0, 0, 0]</code></pre>

  <pre><code>#header {
  color: blue;
}
Specificity: [0, 1, 0, 0]</code></pre>

  <pre><code>.button {
  color: green;
}
div:hover {
  color: green;
}
[type="text"] {
  color: green;
}
Specificity: [0, 0, 1, 0] (each)</code></pre>

  <pre><code>div {
  color: black;
}
Specificity: [0, 0, 0, 1]</code></pre>

  <strong>Combined selectors example:</strong>
  <pre><code>div #header .button {
  color: purple;
}
/* Specificity: [0, 1, 1, 1] */</code></pre>

  <strong>Rules of specificity:</strong>
  <ul>
    <li>Inline styles have the highest specificity.</li>
    <li>ID selectors are more specific than class selectors.</li>
    <li>Class, attribute, and pseudo-class selectors are more specific than element or pseudo-element selectors.</li>
    <li>If specificity is equal, the rule that appears later in the CSS wins.</li>
  </ul>

  <strong>Conflict example:</strong>
  <pre><code>p {
  color: red; /* Specificity: [0, 0, 0, 1] */
}

.someClass {
  color: blue; /* Specificity: [0, 0, 1, 0] */
}

&lt;p class="someClass"&gt;Hello World!&lt;/p&gt;
<!-- Result: blue text --></code></pre>

  <strong>Conclusion:</strong><br />
  The more IDs, classes, and tags a selector includes, the more specific it becomes. Understanding and calculating specificity helps resolve style conflicts effectively.
</details>

<details>
  <summary><strong>54. What is the mobile-first approach, and what are its advantages and disadvantages?</strong></summary>

  <strong>Mobile-first</strong> is a web development approach where design and development start with optimization for mobile devices (small screens), then progressively enhance the experience for larger screens like tablets and desktops. It uses progressive enhancement instead of scaling down from desktop (desktop-first).

  <strong>Advantages of mobile-first:</strong>
  <ul>
    <li><strong>Better user experience on mobile:</strong> UI and functionality are tailored for mobile users, considering limitations like screen size and network speed.</li>
    <li><strong>Faster load times:</strong> Developers are encouraged to optimize performance by minimizing resources like images, fonts, and scripts.</li>
    <li><strong>Focus on core functionality:</strong> The limited screen space pushes developers to prioritize essential features and avoid clutter.</li>
    <li><strong>Simplified responsive design:</strong> It’s easier to scale up using media queries once a solid mobile base is created.</li>
    <li><strong>SEO benefits:</strong> Google prioritizes mobile-friendly websites in its indexing and ranking.</li>
  </ul>

  <strong>Disadvantages of mobile-first:</strong>
  <ul>
    <li><strong>Time-consuming for complex apps:</strong> Developing for mobile first and then adapting to desktop can require more effort for large-scale projects.</li>
    <li><strong>Challenging for feature-rich designs:</strong> Heavy components (like graphics or interactive elements) can be hard to implement effectively on mobile.</li>
    <li><strong>Requires detailed planning:</strong> Proper structure and planning are necessary to ensure a smooth scale-up to desktop, which demands strong architectural understanding.</li>
  </ul>

  <strong>Conclusion:</strong><br />
  The mobile-first approach improves optimization for mobile users and boosts site performance, which is critical with increasing mobile traffic. However, for complex or feature-heavy projects, it may increase development complexity and time.
</details>

<details>
  <summary><strong>54. Explain how specificity is calculated in CSS selectors.</strong></summary>

  <strong>Specificity</strong> in CSS is a mechanism that browsers use to determine which style rule to apply when multiple selectors target the same element. It is based on the types of selectors used, and the more specific a selector is, the higher its priority.

  <strong>How is specificity calculated?</strong><br />
  Specificity is usually represented as a four-part value: <strong>(a, b, c, d)</strong>, where:
  <ul>
    <li><strong>a</strong> – Inline styles (e.g., <code>style="..."</code>)</li>
    <li><strong>b</strong> – Number of ID selectors</li>
    <li><strong>c</strong> – Number of class selectors, attribute selectors, and pseudo-classes</li>
    <li><strong>d</strong> – Number of element names and pseudo-elements</li>
  </ul>

  <strong>Examples:</strong>
  <ul>
    <li><code>p</code> → (0, 0, 0, 1)</li>
    <li><code>.menu</code> → (0, 0, 1, 0)</li>
    <li><code>#header</code> → (0, 1, 0, 0)</li>
    <li><code>style="..."</code> → (1, 0, 0, 0)</li>
    <li><code>div.menu</code> → (0, 0, 1, 1)</li>
    <li><code>#header .menu</code> → (0, 1, 1, 0)</li>
    <li><code>.menu .item</code> → (0, 0, 2, 0)</li>
  </ul>

  <strong>How to calculate total specificity?</strong><br />
  Each part is summed across the selector. For example:<br />
  <code>#header .menu a</code> has:
  <ul>
    <li>#header → (0, 1, 0, 0)</li>
    <li>.menu → (0, 0, 1, 0)</li>
    <li>a → (0, 0, 0, 1)</li>
  </ul>
  Final specificity: <strong>(0, 1, 1, 1)</strong>

  <strong>Priority rules:</strong><br />
  Specificity is compared from left to right: <code>a → b → c → d</code>.
  <ul>
    <li><code>#header .menu</code> → (0, 1, 1, 0)</li>
    <li><code>.menu a</code> → (0, 0, 1, 1)</li>
    <li>First selector wins because of higher specificity.</li>
  </ul>

  <strong>Important notes:</strong>
  <ul>
    <li><code>!important</code> overrides specificity unless both rules use it — then specificity is compared.</li>
    <li>Inherited properties do not affect specificity — direct rules take priority.</li>
  </ul>

  <strong>Conclusion:</strong><br />
  Understanding CSS specificity helps prevent style conflicts. Build selectors carefully and avoid overusing <code>!important</code> to maintain clean and predictable styles.
</details>

<details>
  <summary><strong>55. What are CSS pre-/post-processors used for?</strong></summary>

  <strong>CSS pre- and post-processors</strong> are tools that extend standard CSS functionality, making it easier to write structured, scalable, and maintainable style code.

  <strong>CSS Preprocessors:</strong><br />
  Preprocessors use their own syntax, which compiles to regular CSS. They introduce features like variables, nested selectors, mixins, and functions.

  <strong>Popular preprocessors:</strong>
  <ul>
    <li><strong>Sass/SCSS</strong> — widely used, supports both Sass and SCSS syntax.</li>
    <li><strong>LESS</strong> — similar to SCSS with its own syntax quirks.</li>
    <li><strong>Stylus</strong> — allows very flexible syntax, including omission of brackets and semicolons.</li>
  </ul>

  <strong>Main features:</strong>
  <ul>
    <li><strong>Variables:</strong> Reuse colors, sizes, or fonts.<br />
      <code>$primary-color: #3498db;</code><br />
      <code>body { background-color: $primary-color; }</code>
    </li>
    <li><strong>Nested selectors:</strong> Better structure and DRY code.<br />
      <code>.menu { a { color: #333; } }</code>
    </li>
    <li><strong>Mixins:</strong> Reusable blocks of styles with arguments.<br />
      <code>@mixin border-radius($radius) { border-radius: $radius; }</code><br />
      <code>.box { @include border-radius(10px); }</code>
    </li>
    <li><strong>Functions:</strong> Do calculations, color manipulation.<br />
      <code>$base-color: #3498db;</code><br />
      <code>.box { color: lighten($base-color, 20%); }</code>
    </li>
    <li><strong>Inheritance:</strong> Reuse styles via <code>@extend</code>.<br />
      <code>.primary-button { @extend .button; }</code>
    </li>
  </ul>

  <strong>CSS Postprocessors:</strong><br />
  Postprocessors modify already written CSS, mainly for compatibility and optimization.

  <strong>Most used postprocessor:</strong>
  <ul>
    <li><strong>Autoprefixer</strong> — adds vendor prefixes based on browser support data.</li>
  </ul>

  <strong>Example:</strong><br />
  Input:
  <pre><code>.box {
  display: flex;
}</code></pre>
  Output with Autoprefixer:
  <pre><code>.box {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}</code></pre>

  <strong>Postprocessor features:</strong>
  <ul>
    <li>Automatic vendor prefixing for cross-browser support</li>
    <li>CSS minification and deduplication</li>
    <li>Converting modern CSS (CSS4) to older CSS (CSS3) for compatibility</li>
  </ul>

  <strong>Benefits of preprocessors and postprocessors:</strong>
  <ul>
    <li>Better code structure (via variables, mixins, nesting)</li>
    <li>Faster development with reusable logic</li>
    <li>Improved browser support</li>
    <li>More maintainable and scalable CSS</li>
  </ul>

  <strong>Drawbacks:</strong>
  <ul>
    <li>Require a compilation step</li>
    <li>Dependency on third-party tools</li>
    <li>Extra complexity for beginners</li>
  </ul>

  <strong>Conclusion:</strong><br />
  CSS preprocessors help write flexible and DRY code, while postprocessors enhance compatibility and reduce manual overhead. Both tools are essential in modern frontend workflows.
</details>

<details>
  <summary><strong>56. What are the types of inputs in forms? How to submit a form to the server without JavaScript?</strong></summary>

  <strong>Types of inputs in HTML forms:</strong>
  <ul>
    <li><code>&lt;input type="text"&gt;</code> — text field for entering text.</li>
    <li><code>&lt;input type="password"&gt;</code> — password field (hidden text).</li>
    <li><code>&lt;input type="email"&gt;</code> — email input (validates email format).</li>
    <li><code>&lt;input type="number"&gt;</code> — numeric input field.</li>
    <li><code>&lt;input type="tel"&gt;</code> — phone number input.</li>
    <li><code>&lt;input type="url"&gt;</code> — URL input field.</li>
    <li><code>&lt;input type="date"&gt;</code> — date picker.</li>
    <li><code>&lt;input type="radio"&gt;</code> — radio buttons (select one option).</li>
    <li><code>&lt;input type="checkbox"&gt;</code> — checkboxes (select multiple options).</li>
    <li><code>&lt;input type="file"&gt;</code> — file upload input.</li>
    <li><code>&lt;input type="submit"&gt;</code> — button to submit the form.</li>
    <li><code>&lt;input type="reset"&gt;</code> — button to reset form fields to initial values.</li>
    <li><code>&lt;input type="hidden"&gt;</code> — hidden input, not visible but sent to server.</li>
    <li><code>&lt;input type="color"&gt;</code> — color picker.</li>
    <li><code>&lt;input type="range"&gt;</code> — slider for selecting value in a range.</li>
    <li><code>&lt;input type="search"&gt;</code> — search query input.</li>
    <li><code>&lt;textarea&gt;</code> — multiline text input (not an input element but used for text).</li>
    <li><code>&lt;select&gt;</code> — dropdown list for single or multiple selection.</li>
  </ul>

  <strong>Submitting a form to the server without JavaScript:</strong><br />
  Use the standard HTML <code>&lt;form&gt;</code> element with <code>action</code> and <code>method</code> attributes.<br />

  <strong>Example:</strong>
  <pre><code>&lt;form action="/submit-url" method="POST"&gt;
  &lt;label for="name"&gt;Name:&lt;/label&gt;
  &lt;input type="text" id="name" name="name" required&gt;

  &lt;label for="email"&gt;Email:&lt;/label&gt;
  &lt;input type="email" id="email" name="email" required&gt;

  &lt;input type="submit" value="Submit"&gt;
&lt;/form&gt;
  </code></pre>

  <strong>Explanation:</strong>
  <ul>
    <li><code>action="/submit-url"</code> — URL where form data is sent (usually a server endpoint).</li>
    <li><code>method="POST"</code> — HTTP method for data submission:
      <ul>
        <li><code>POST</code> sends data in the request body (used to create/update data).</li>
        <li><code>GET</code> sends data via URL query string (used for retrieving data).</li>
      </ul>
    </li>
    <li><code>&lt;input type="submit"&gt;</code> — button to send form data to the server.</li>
  </ul>

  <strong>How it works:</strong><br />
  When the user clicks the submit button, form data is sent to the URL specified in <code>action</code> using the specified <code>method</code>. The server then processes the data (e.g., stores it in a database).

  <strong>Advantages:</strong>
  <ul>
    <li>Simple and effective way to send data without dependencies or scripting.</li>
  </ul>

  <strong>Disadvantages:</strong>
  <ul>
    <li>Less control over form submission (no dynamic validation or data manipulation before sending).</li>
  </ul>
</details>

