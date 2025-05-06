<details>
<summary>1. What is the purpose of semantic HTML? When and where is it important? </summary>

Semantic HTML provides meaning to the web page structure by using tags that reflect the purpose of the content inside them 
(`<article>`, `<section>`, `<header>`, etc.).

**Why it’s important:**

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
