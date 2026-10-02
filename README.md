# JavaScript DOM & Event Handling

This repository contains my practice work on JavaScript DOM manipulation and event handling.

## Questions and Answers

### 1. What is the difference between `getElementById`, `getElementsByClassName`, and `querySelector` / `querySelectorAll`?

**Answer:**

Here is the difference between `getElementById`, `getElementsByClassName`, `querySelector`, and `querySelectorAll`:

#### `getElementById()`

* Finds an element by `id`.
* Returns one element.

#### `getElementsByClassName()`

* Finds elements by class.
* Returns many elements as an `HTMLCollection`.

#### `querySelector()`

* Uses a CSS selector.
* Returns the first matching element.

#### `querySelectorAll()`

* Uses a CSS selector.
* Returns all matching elements as a `NodeList`.

---

### 2. How do you create and insert a new element into the DOM?

**Answer:**

#### Create an element:

```javascript
let div = document.createElement("div");
```

#### Insert into the DOM:

```javascript
document.body.appendChild(div);
```

This adds the new element at the end of the body.

---

### 3. What is Event Bubbling? And how does it work?

**Answer:**

Event bubbling is when an event triggered on a child element also triggers on its parent, then grandparent, then body, then document.

Event travels from **inside → outside**.

#### How it works:

When we click a child element, the event triggers on the child element first, and then it automatically triggers on its parent, then the body, then the document.

**Order:**

```text
Child → Parent → Body → Document
```

#### Example:

Click a button inside a `div`:

```text
Button event triggers
        ↓
Div event triggers
        ↓
Body event triggers
        ↓
Document event triggers
```

---

### 4. What is Event Delegation in JavaScript? Why is it useful?

**Answer:**

Event Delegation means adding an event listener to a parent element instead of adding it to many child elements.

The parent element then responds to the event when any child element is clicked, using event bubbling.

#### Example:

Instead of adding a click event to 100 buttons, we add one event to their parent.

```javascript
document.getElementById("parent").addEventListener("click", function(event) {
    if (event.target.classList.contains("btn")) {
        console.log("Button clicked");
    }
});
```

#### Why is it useful?

* Less code
* Better performance
* Works for dynamically added elements
* Easy to manage events

---

### 5. What is the difference between `preventDefault()` and `stopPropagation()` methods?

**Answer:**

Here's the difference:

#### `preventDefault()`

This stops the default behavior of an element.

For example:

* If we click a link (`<a>`), it normally opens another page.
* If we submit a form, it normally reloads the page.

```javascript
event.preventDefault();
```

This stops that default action.

So:

* Link won't go to another page.
* Form won't reload.
* But the event can still bubble up.

#### `stopPropagation()`

This stops the event from moving up to parent elements.

```javascript
event.stopPropagation();
```

The event will run only on that element and won't go to the parent, body, or document.

---

## DOM (Document Object Model)

The **DOM** is a programming interface that represents an HTML document as a tree of objects.

JavaScript uses the DOM to access, change, add, or remove HTML elements and their content.

### Example

HTML:

```html
<h1 id="title">Hello World</h1>
```

JavaScript:

```javascript
const title = document.getElementById("title");

title.textContent = "Hello JavaScript";
```

Here, JavaScript selects the `<h1>` element from the DOM and changes its text.

### Common DOM Operations

```text
Select elements
     ↓
Create elements
     ↓
Change content
     ↓
Change attributes/styles
     ↓
Add or remove elements
```

---

## DOM Event Handling

An **event** is an action that happens in the browser, such as:

* `click`
* `submit`
* `input`
* `change`
* `mouseover`
* `keydown`

JavaScript can listen for these events using `addEventListener()`.

### Example

```javascript
const button = document.getElementById("button");

button.addEventListener("click", function() {
    console.log("Button clicked");
});
```

When the user clicks the button, the event listener runs the function.

---

## Event Flow

When an event occurs, it can move through different phases of the DOM.

```text
Capturing Phase
       ↓
Target Phase
       ↓
Bubbling Phase
```

Event bubbling is especially useful for **Event Delegation**, where a parent element handles events from its child elements.

---

## Key Concepts

This project covers the following JavaScript concepts:

* DOM
* DOM Element Selection
* `getElementById()`
* `getElementsByClassName()`
* `querySelector()`
* `querySelectorAll()`
* Creating DOM Elements
* `appendChild()`
* Event Handling
* Event Bubbling
* Event Delegation
* `event.target`
* `preventDefault()`
* `stopPropagation()`

## Technologies Used

* HTML5
* CSS3
* JavaScript
* DOM API

## GitHub: [FahmidaAkterShimu](https://github.com/FahmidaAkterShimu)
