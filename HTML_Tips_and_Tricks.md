
# HTML Tips and Tricks ✨

In my very last article, I shared some JavaScript tips and tricks. In this article, I will be covering HTML tips and tricks ✨.

## The `start` Attribute

The `start` attribute allows you to specify a starting number for your list items.

```html
<ol start="20">
    <li>Pineapple 🍍</li>
    <li>Apple 🍎</li>
    <li>Greenapple 🍏</li>
</ol>
```

3 items of fruits starting from 20. The number `20` is specified using the `start` attribute.

---

## The `contenteditable` Attribute

Set the `contenteditable` attribute to `true`, and your content will be editable.

```html
<p contenteditable="true">It can be something about you.</p>
```

Illustration of an editable paragraph achieved using the `contenteditable` attribute.

---

## The `required` Attribute

Set the `required` attribute on input fields that are mandatory to be filled.

```html
<input type="password" required>
```

---

## The `<mark>` Tag

Use the `<mark>` tag instead of styling spans to highlight text.

```html
<p>This is <mark>important</mark></p>
```

Highlighted text achieved with the `<mark>` tag.

---

## The `lazy` Loading Attribute

Add the `loading="lazy"` attribute on media elements to enhance page performance by deferring the loading of media elements until the user scrolls to them.

```html
<img src="image.jpg" loading="lazy" alt="Alternative text">
```

---

## The `<kbd>` Tag

Use the `<kbd>` tag when presenting keyboard inputs.

```html
<p>Press <kbd>alt</kbd> & <kbd>tab</kbd> to change window</p>
```

Illustration for the `<kbd>` tag.

---

## The `<details>` & `<summary>` Tags

You can craft nice-looking accordions using the `<details>` and `<summary>` elements. These have built-in keyboard accessibility features.

```html
<details>
    <summary>Can I save and love ❤️ this article?</summary>
    <p>Follow on Twitter for more stuff.</p>
    <p>Save for updates.</p>
</details>
```

Accordion with a question and answer.

---

## The `accept` Attribute

The `accept` attribute allows you to specify which types of files the user can upload.

```html
<input type="file" accept=".jpg, .pdf">
```

---

## The Favicon

Set `link rel="icon"` to define a favicon.

```html
<link rel="icon" href="logo.webp">
```

---

## The `<picture>` Tag

The `<picture>` tag allows you to present images of different aspect ratios based on screen sizes. It is awesome for implementing responsive web design.

```html
<picture>
    <source srcset="large.webp" media="(min-width: 1200px)">
    <source srcset="medium.webp" media="(min-width: 800px)">
    <img src="regular.jpg" />
</picture>
```

---

## The `dir` Attribute

You can set your text direction from right-to-left or left-to-right using the `dir` attribute. Set `dir="auto"` to automatically change text direction based on language.

```html
<p dir="rtl">Awesome!</p>
```

Some text written from right to left.

---

## The `spellcheck` Attribute

Use the `spellcheck` attribute to check for spelling errors.

```html
<input type="email" spellcheck="true">
```

---

## The Meta Description

Add meta descriptions in the `<head>` of your HTML to have an indirect impact on search engine optimization. The meta description represents the text that appears beneath the site name on the search engine result page.

```html
<meta name="description" content="Gitpod streamlines developer workflows by providing prebuilt, collaborative developer environments in your browser - powered by VS Code.">
```

---

## The `<abbr>` Tag

Abbreviate your content using the `<abbr>` tag.

```html
<abbr title="National Aeronautics and Space Administration">NASA 🚀</abbr>
```

Abbreviation of the word shown on hover over the word.

---

## The `disabled` Attribute

Use the `disabled` attribute for the `<option>` element to disable an item from the dropdown.

```html
<select>
    <option>HTML</option>
    <option>CSS</option>
    <option disabled>REACT</option>
</select>
```

Unable to select an option from the list because of the `disabled` attribute.

---

## The `poster` Attribute

The `poster` attribute allows you to specify an image to be displayed while the video is downloading or until the user hits the play button.

```html
<video src="video.mp4" poster="flowers.jpg"></video>
```

---

## The `reversed` Attribute

Using the `reversed` attribute, you can reverse the order of list numbers.

```html
<ol reversed>
    <li>Pineapple 🍍</li>
    <li>Apple 🍎</li>
    <li>Greenapple 🍏</li>
</ol>
```

List numbers starting in reversed order, from 3 to 1 instead of 1 to 3.

---

Hope you enjoyed reading this article! If you have something to say or have any questions, feel 💯 free to comment below.

Happy Coding ✨❤️
