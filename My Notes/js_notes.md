# My JavaScript Notes

## Using Console
Messages can be logged to the console using the `console.log()` method.

`Sample code:`
```js
console.log('Hello World'); // Displays a string in the console
console.log(123); // Displays a number in the console
console.log(true); // Displays a boolean value in the console
console.log([1,2,3,4]); // Displays an array in the console
```

In addition, *error* as well as *warning* messages can be displayed in the console.

`Sample code:`
```js
console.error('This is some error'); // Displays an error message in the console
console.warn('This is a warning'); // Displays a warning in the console
```

`console.clear()` method can be used to *clear* the console.

---
<br>

## Variables - var, let & const
Javascript has 3 kinds of variable declarations: `var`, `let` and `const`.  
`var` - Declares a variable, optionally initializing it to a value.  
`let` - Declares a block-scoped, local variable, optionally initializing it to a value.  
`const` - Declares a block-scoped, read-only named constant.

### Naming convention
We use variables as symbolic names for values in our program. The names of variables, called *identifiers*, follow the following naming conventions:
- Variable names can contain *letters, numbers, _ and $*
- Variable names cannot start with a number
- Multi-word variable names normally use camelCase

### *var*
`var` can be used to declare both **local** and **global** variables, depending on the execution context.  
`Syntax:`  
```js
var age = 42;
```

### *let* and *const*
`let` and `const` can be used to declare a block-scope local variable.


`const` stands for read-only, named constants which means they cannot be reassigned. In javascript, a constant must be initialized when it is declared (*Why? Because it is a constant and it's needs an initial value to begin with, duh.*).

`Sample code:`
```js
const PI = 3.14; // constant declaration & initialization
console.log(PI);

let name = 'Deepak'; // created a variable named 'name' and assigns it the value 'Deepak'
console.log(name);
```
---
<br>

## Data Types in Javascript
`Primitive Data Types:`
- Accessed by the actual value
- Stored directly at the location the variable accesses
- Stored in the stack

There are 6 primitive data types:
1. String
2. Number
3. Boolean
4. Null (intentional empty value)
5. Undefined (variable that has not been assigned a value)
6. Symbols

`Reference Data Types:`
- Accessed by reference
- Objects that are stored on the heap (dynamically allocated memory)
- A pointer to a location in memory

Some of the referece types are:
1. Arrays
2. Object Literals
3. Functions
4. Dates

`Note: Javascript is a dynamically typed language. This means, the same variable name can hold multiple types. We do not need to specify types.`

---
<br>

## Understanding the DOM (Document Object Model)
Document Object Model(DOM) is the structured representation of an HTML document. It can be thought of as a tree of nodes/elements created by the browser. We can use JavaScript to read from/write to/manipuate the DOM. The DOM is `object oriented`, meaning that each node has its own set of properties and methods that we can change, we can add, we can remove.

### DOM Element Selectors
DOM Selectors can be classified into two: `Single element selectors` and `Multiple element selectors`.

#### Single Element selectors
Allows you to grab an element by its ID, class etc. and stores only one element. So if you have multiple elements that satisfy the criteria used in the selector, the single element selector selects the *first element which satisfies the criteria*.


**getElementById()**  
`document.getElementById((elementId: string): HTMLElement)`  
Returns the first `HTMLElement` that has the ID `elementId`.

**.querySelector()**  
`document.querySelector<Element>(selectors: string): Element`  
Allows you to select a single element by using any `CSS selector`.


#### Multiple Element selectors
Allows you to grab all the elements that satisfy a criteria(e.g.: class, tag name etc.). So if you have multiple elements that satisfy the criteria used in the selector, the multiple element selector selects *all of the elements that satisfy the criteria* and return an *HTML Collection or Node List depending on the selector being used*.

**getElementsByClassName()**  
`Document.getElementsByClassName(classNames: string): HTMLCollectionOf<Element>`  
Returns an HTMLCollection of the elements in the object on which the method was invoked (a document or an element) that have all the classes given by classNames. The `classNames` argument is interpreted as a space-separated list of classes.

**getElementsByTagName()**  
`Document.getElementsByTagName(qualifiedName: string): HTMLCollectionOf<HTMLLIElement>`  
Retrieves a collection of objects based on the specified `element name`.

**querySelectorAll()**  
`ParentNode.querySelectorAll(selectors: string): NodeListOf<HTMLUListElement>`  
Returns all element descendants of node that match selectors.

---
<br>

##  Event Handlers
Using JavaScript, we can register functions as *`handlers`* for specific events.

`For example:`
```js
window.addEventListener("click", function(e) {
    console.log("My first event handler!!!");
  });
```
*The `window` binding refers to a built-in object provided by the browser. It represents the browser window that contains the document. Calling its `addEventListener()` method registers the second argument to be called whenever the event described by its first argument occurs.*

**Note:**
*The `removeEventListener()` method, called with arguments similar to `addEventListener()`, removes a handler.*

### Event Default Actions
Many events have a default action associated with them. However, for most types of events, the JavaScript event handlers are called *before* the event behavior takes place. If you want to prevent this normal behavior from happening, you can call the `preventDefault()` method on the event object.

`Sample Code:`
```js
document.forms.loginForm.addEventListener('submit', function(e) {
    e.preventDefault();
})
```

### Propagation
For most event types, handlers registered on nodes with children will also receive events that happen in the children. However, the more specific handler - the one registered on the child - gets to go first. The event is said to *propagate* outward, from the node where it happened to its parent nodes, until it finally reaches the root of the document.

**Note:** *At any point, an event handler can call the `stopPropagation()` method on the event object to prevent handlers further up from receiving the event.*

### target vs currentTarget
Most event objects have a `target` property that refers to the node where they `originated`.

The `currentTarget` property for an event identifies the current target for the event, as it traverses the DOM. In simple words, it always refers to the element to which the event handler has been attached, as opposed to `Event.target`, which identifies the element on which the event occurred and which may be its descendant.

### Key Events
When a key on the keyboard is pressed, the browser fires a `keydown` event. Similarly, when a key is released, the browser fires a `keyup` event.

### Pointer Events
There are currently two widely used ways to point at things on a screen: mice (including devices that act like mice, such as touchpads and trackballs) and touchscreens. These produce different kinds of events.

#### Mouse clicks
Pressing a mouse button causes a number of events to fire. The `mousedown` and `mouseup` events are similar to `keydown` and `keyup` events and fire when the mouse button is pressed and released. These events happen on the DOM elements(nodes) that are immediately beneath teh mouse pointer when the event occurs.

After the `mouseup` event, a `click` event fires on the most specific node that contained both the press and the release of the button.

If two clicks happen close together, a `dblclick` (double-click) event also fires, after the second click event.

To get precise information about the place where a mouse event happened, you can look at its *`clientX`* and *`clientY`* properties, which contain the event’s *coordinates (in pixels) relative to the top-left corner of the window,* or **`pageX`** and **`pageY`**, which are **relative to the top-left corner of the whole document** (which may be different when the window has been scrolled).

#### Mouse Motion
Every time the mouse pointer moves, a `mousemove` event is fired. This event can be used to track the position of the mouse. A common situation in which this is useful is when implementing some form of mouse-dragging functionality.