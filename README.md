# HTML Classes & IDs

**Frontend Development · Vanier College · Winter 2026**

---

## Today's Roadmap

| # | Topic | Time |
|---|-------|------|
| 01 | What are Attributes? | 15 min |
| 02 | The `id` Attribute | 25 min |
| 03 | The `class` Attribute | 25 min |
| 04 | `id` vs `class` | 20 min |
| 05 | Live Coding Examples | 25 min |
| 06 | Best Practices & Wrap-up | 10 min |

---

## HTML Tags Used in This Workshop

Before we dive in, here is a quick reference for every HTML tag that appears in the examples throughout this document. If any of these are new to you, take a moment to read through them now — you will see them all in action shortly.

| Tag | Purpose | Example |
|-----|---------|---------|
| `<h1>`, `<h2>`, `<h3>` | Headings, from largest to smallest. Use `<h1>` for the main page title, `<h2>` for section titles, `<h3>` for sub-section titles. | `<h1>Welcome</h1>` |
| `<p>` | A paragraph of text. | `<p>Hello world</p>` |
| `<a>` | A hyperlink. The `href` attribute sets the destination URL. | `<a href="https://example.com">Click</a>` |
| `<img>` | An image. Self-closing tag. `src` sets the file path, `alt` provides a text description. | `<img src="photo.jpg" alt="Sunset">` |
| `<div>` | A generic container with no meaning on its own. Used to group elements for styling. | `<div class="card">...</div>` |
| `<span>` | An inline generic container. Used to style a small piece of text or content within a line. | `<span class="tag">HTML</span>` |
| `<nav>` | Wraps a set of navigation links. Tells the browser "this is a menu". | `<nav>...</nav>` |
| `<header>` | The introductory area of a page or section, typically containing a logo and navigation. | `<header>...</header>` |
| `<main>` | The primary content of the page. There should only be one per page. | `<main>...</main>` |
| `<footer>` | The closing area of a page or section, typically containing copyright or contact info. | `<footer>...</footer>` |
| `<section>` | A thematic grouping of content, usually with its own heading. | `<section id="about">...</section>` |
| `<article>` | A self-contained piece of content that could stand alone, like a blog post or news story. | `<article class="post">...</article>` |
| `<button>` | A clickable button. | `<button class="btn">Submit</button>` |

The tags `<header>`, `<main>`, `<footer>`, `<section>`, `<article>`, and `<nav>` are called **semantic tags** — they describe the *meaning* of their content, not just how it looks. Using them makes your HTML clearer for both developers and browsers.

---

## 1 · What Are HTML Attributes?

Attributes provide additional information about HTML elements. They sit inside the opening tag and follow a `name="value"` pattern.

```html
<a href="https://example.com" target="_blank">Click me</a>

<img src="photo.jpg" alt="A sunset" width="300">

<p id="intro" class="highlight">Hello!</p>
```

There are many kinds of attributes — `href`, `src`, `alt`, `style`, `width` — but today we focus on the **two most important ones for CSS**: **`id`** and **`class`**.

---

## 2 · The `id` Attribute

### What is it?

An `id` is a **unique identifier** for a single element on the page. Think of it like a student ID number — no two students share the same one.

### Rules

- **Must be unique** — only ONE element per page can have a given `id`.
- **Starts with a letter** — can then contain letters, digits, hyphens, underscores.
- **Case-sensitive** — `"myNav"` and `"mynav"` are different.
- **No spaces** — use hyphens: `id="main-header"`, not `id="main header"`.

### HTML Example

```html
<h1 id="page-title">Welcome</h1>
<nav id="main-nav">...</nav>
<div id="hero-section">...</div>
```

### Targeting `id` in CSS — the `#` selector

```css
#page-title {
  color: navy;
  font-size: 2rem;
}

#main-nav {
  background: #1E293B;
  padding: 10px 20px;
}

#hero-section {
  min-height: 400px;
  background: lightblue;
}
```

### A Quick Peek at JavaScript

You don't need to know JavaScript yet, but it's good to know that `id` is used by JS to grab a single element:

```js
document.getElementById("page-title");
```

This is the fastest way for JS to find one specific element — and it only works with `id`.

### Bonus — Anchor Links

IDs also let you create jump links. Clicking the link scrolls the page directly to that section:

```html
<!-- Navigation -->
<a href="#about">Go to About</a>
<a href="#contact">Go to Contact</a>

<!-- Sections -->
<section id="about">
  <h2>About Us</h2>
</section>

<section id="contact">
  <h2>Contact</h2>
</section>
```

---

## 3 · The `class` Attribute

### What is it?

A `class` is a **reusable label** you can apply to many elements. Think of it like a t-shirt color — many students can wear blue, and they all belong to the "blue" group.

### Rules

- **Reusable** — many elements can share the same class.
- **Multiple classes** — one element can have several classes separated by spaces.
- **Not unique** — unlike `id`, `class` is designed to be repeated.
- **CSS uses dot (.)** — select with `.classname`.

### HTML + CSS Example

```html
<p class="highlight">First paragraph</p>
<p class="highlight">Second paragraph</p>
<p>Normal paragraph</p>
```

```css
/* One rule styles BOTH highlighted paragraphs! */
.highlight {
  background: yellow;
  font-weight: bold;
}
```

### Multiple Classes on One Element

This is one of the most powerful features of `class` — you can combine them to build modular, reusable styles.

```html
<button class="btn btn-primary btn-large">Sign Up</button>
<button class="btn btn-danger btn-small">Delete</button>
<button class="btn btn-outline">Cancel</button>
```

```css
/* Base style */
.btn {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

/* Variations */
.btn-primary { background: #06B6D4; color: white; }
.btn-danger  { background: #EF4444; color: white; }
.btn-outline { background: none; border: 2px solid #333; }

/* Sizes */
.btn-large { font-size: 18px; padding: 15px 30px; }
.btn-small { font-size: 12px; padding: 5px 10px; }
```

> This is exactly how frameworks like Bootstrap and Tailwind CSS work — composable utility classes!

### A Quick Peek at JavaScript

Again, just for awareness — JS can grab all elements that share a class:

```js
document.getElementsByClassName("highlight");
```

This returns **all** elements with that class, not just one.

---

## 4 · `id` vs `class` — The Key Differences

| Feature | `#id` | `.class` |
|---------|-------|----------|
| Uniqueness | Must be unique on page | Can be reused many times |
| Per element | Only ONE id | MULTIPLE classes allowed |
| CSS selector | `#` (hash) | `.` (dot) |
| Best for | Single unique elements | Groups of similar elements |
| JS method | `getElementById()` | `getElementsByClassName()` |
| URL anchors | Yes — `href="#id"` | No |

### The Analogy

| | `id` | `class` |
|-|------|---------|
| **Real-world analogy** | Your student ID number | Your t-shirt color |
| **How many?** | Only ONE person has it | MANY people can share it |
| **When called** | "ID #42069!" → one person stands up | "All blue shirts!" → multiple people stand up |
| **In code** | `id="student-42069"` | `class="blue-team"` |

---

## 5 · Live Coding Examples

### Example 1 — Navigation Bar

```html
<nav id="main-nav">
  <a href="#" class="nav-link active">Home</a>
  <a href="#" class="nav-link">About</a>
  <a href="#" class="nav-link">Blog</a>
  <a href="#" class="nav-link">Contact</a>
</nav>
```

```css
/* id → only ONE navbar on the page */
#main-nav {
  background: #1E293B;
  display: flex;
  padding: 0 20px;
}

/* class → MULTIPLE links share the same style */
.nav-link {
  color: white;
  padding: 15px 20px;
  text-decoration: none;
}

.nav-link:hover {
  background: #334155;
}

/* combining classes → mark the current page */
.nav-link.active {
  border-bottom: 3px solid #06B6D4;
}
```

**Key observations:**
- `id="main-nav"` — only one navbar exists → use `id`
- `class="nav-link"` — multiple links share styling → use `class`
- `class="nav-link active"` — combining classes to mark the current page

---

### Example 2 — Product Cards

```html
<section id="products">

  <div class="card">
    <img class="card-img" src="shoe.jpg">
    <h3 class="card-title">Running Shoe</h3>
    <p class="card-price">$89.99</p>
    <button class="btn btn-primary">Add to Cart</button>
  </div>

  <div class="card card-featured">
    <img class="card-img" src="jacket.jpg">
    <h3 class="card-title">Winter Jacket</h3>
    <p class="card-price sale">$149.99</p>
    <button class="btn btn-primary">Add to Cart</button>
  </div>

</section>
```

**What's happening here:**
- `id="products"` — unique section wrapper
- `.card` — reused for every product
- `.card-featured` — modifier class for the special card
- `.card-img`, `.card-title`, `.card-price` — shared component styles
- `.btn .btn-primary` — composable button classes
- `.sale` — additional modifier for discounted prices

---

## Common Mistakes to Avoid

### WRONG — Duplicate IDs

```html
<!-- WRONG — two elements with the same id -->
<p id="text">First</p>
<p id="text">Second</p>
```

```html
<!-- CORRECT — use class for shared styling -->
<p class="text">First</p>
<p class="text">Second</p>
```

### WRONG — Multiple IDs on One Element

```html
<!-- WRONG -->
<div id="box" id="container">
```

```html
<!-- CORRECT — one id + classes -->
<div id="box" class="container">
```

### WRONG — Accidental Multiple Classes from Spaces

```html
<!-- This creates THREE separate classes: "my", "text", "here" -->
<p class="my text here">

<!-- Use hyphens for multi-word class names -->
<p class="my-text-here">
```

---

## Which Should I Use? — Decision Guide

```
Is this element unique on the page?
├── YES → Do you need anchor links or a unique CSS target?
│   ├── YES → Use id
│   └── NO  → Use class (still safer)
└── NO  → Use class
```

> **Pro tip: When in doubt, use `class`.** It's more flexible and easier to maintain.

---

## 6 · Best Practices

1. **Prefer `class` over `id` for styling** — classes keep specificity low and CSS maintainable.
2. **Use meaningful names** — `class="card-header"` not `class="ch"` or `class="blue-text"`.
3. **Use hyphens for multi-word names** — `class="nav-link"` is consistent and readable.
4. **Reserve `id` for anchors and unique landmarks** — headers, footers, main nav.
5. **Never style with `id` if `class` works** — high-specificity ids create cascading headaches.
6. **Name by purpose, not appearance** — `.error-message` not `.red-bold`.

---

## Quick Quiz — `id` or `class`?

| Scenario | Answer | Why? |
|----------|--------|------|
| The main page header | `id` | Only one per page |
| All product cards in a grid | `class` | Multiple elements |
| A form's submit button | `id` | Unique element |
| Warning messages across the site | `class` | Reusable styling |
| The footer copyright section | `id` | Unique section |
| Navigation links | `class` | Multiple similar links |

---

## Key Takeaways

- **`id`** = unique, one per page, high specificity, selected with `#` in CSS
- **`class`** = reusable, multiple per element, low specificity, selected with `.` in CSS
- Prefer **`class`** for styling — keeps your CSS flexible and maintainable
- Use **`id`** for anchor links and unique page landmarks
- Name by **purpose**, not appearance — `.error-message` not `.red-bold`
- When in doubt, **use `class`** — it's the safer, more scalable choice

---

## Practice Exercise — Build a Blog Page

Use both `id` and `class` to build a simple blog page:

```html
<header id="blog-header">
  <h1>My Blog</h1>
  <nav id="blog-nav">
    <a href="#" class="nav-link active">Home</a>
    <a href="#" class="nav-link">Archive</a>
  </nav>
</header>

<main id="blog-content">
  <article class="post">
    <h2 class="post-title">First Post</h2>
    <span class="tag tag-html">HTML</span>
    <span class="tag tag-css">CSS</span>
    <p class="post-excerpt">Learning about...</p>
    <a href="#" class="btn btn-read-more">Read More</a>
  </article>
  <!-- Add 2 more .post articles! -->
</main>

<footer id="blog-footer">
  <p class="copyright">© 2026</p>
</footer>
```
