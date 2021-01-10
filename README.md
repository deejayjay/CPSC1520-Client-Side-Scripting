# Basic markdown writing and formatting tips
__References:__
[Github Docs](https://docs.github.com/en/free-pro-team@latest/github/writing-on-github/basic-writing-and-formatting-syntax), [Markdown Guide](https://www.markdownguide.org/cheat-sheet/)

## Headings
To create a heading, add one to six # symbols before your heading text. The number of # you use will determine the size of the heading.

Example:
```md
# The largest heading
## The second largest heading
###### The smallest heading
```  
will be displayes as follows:  
# The largest heading
## The second largest heading
###### The smallest heading

---
<br />

## Bold,  *italics* and ~~strikethrough~~
In order to make a block of text **bold**, enclose it between **double asterics** or __double underscore__`(**example**)` or `(__example__)`.

In order to make a block of text *italics*, enclose it between *single asterics* or _single underscore_`(*example*)` or `(_example_)`.

In order to create a ~~crossed out text~~, enclose it between ~~double tildas~~ `(~~example~~)`.

---
<br />

## Block quotes
You can quote a text by adding a > before it.

For example, consider the following markdown:

```md
This is just  some random text. Lorem ipsum dolor sit amet consectetur adipisicing elit. 
>Omnis optio earum neque impedit voluptas distinctio molestiae, numquam modi, temporibus minus qui, eum quam necessitatibus in suscipit consequatur quisquam quia totam.
```

It will be displayed as follows:

This is just  some random text. Lorem ipsum dolor sit amet consectetur adipisicing elit. 
> Omnis optio earum neque impedit voluptas distinctio molestiae, numquam modi, temporibus minus qui, eum quam necessitatibus in suscipit consequatur quisquam quia totam.

## Quoting code
You can call out code or a command within a sentence with `single backticks`. The text within the backticks will not be formatted.   

For instance:  
`<h1>This is a header</h1>`

To format code or text into its own distinct block, use ```triple backticks```.

Check the following example:
```html
<nav>
        <ul>
            <li>Menu 1</li>
            <li>Menu 2</li>
            <li>Menu 3</li>
            <li>Menu 4</li>
        </ul>
    </nav>
```

---
<br />

## Lists
`Unordered Lists`  
You can make an unordered list by preceding one or more lines of text with - or *.

Example:
```md
- List Item 1
- List Item 2
- List Item 3
```
will be displayed as:
- List Item 1
- List Item 2
- List Item 3


`Ordered Lists`  
To order your list, precede each line with a number.

Example:
```md
1. List Item 1
2. List Item 2
3. List Item 3
```
will be displayed as:
1. List Item 1
2. List Item 2
3. List Item 3

---
<br />

## Links
You can create an inline link by wrapping link text in brackets [ ], and then wrapping the URL in parentheses ( ).

Example:  
```md
This site was built using [GitHub Pages](https://pages.github.com/).
```
will be displayed as:  
This site was built using [GitHub Pages](https://pages.github.com/).


