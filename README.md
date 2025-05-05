<details>
<summary>What is the purpose of semantic HTML? When and where is it important? </summary>

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
<summary>How can you style checkboxes in HTML/CSS? </summary>

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
<summary>What can a form consist of? What are the main attributes of a form and its elements, and what do they do? How to validate a form?</summary>

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
  <summary>
    What is the difference between PNG and JPG? What are the advantages of SVG?
  </summary>
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
