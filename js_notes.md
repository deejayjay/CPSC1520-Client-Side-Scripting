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
