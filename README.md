
# An Introduction to CSS

## Introduction
On their own, HTML documents contain the information you want, but may not look very good. Cascading StyleSheets (CSS) is the language used to make websites look attractive.

CSS usually lives separately from the HTML elements and has a different look and feel ("syntax"). CSS directives give web pages their specific look and feel.  If you have ever been impressed by how a website can be displayed on a desktop browser while the same content looks great on a mobile device, you have CSS to thank for it!


## Objectives
You will be able to:
* Recognize the differences between HTML and CSS
* Explain what CSS is and what it's used for
* Add some CSS to a simple web page to style it

## The Power of CSS

One of the most amazing displays of the power of CSS is the
[CSS Zen Garden](http://www.csszengarden.com/) where people take the _exact
same_ HTML page and use CSS to create _wildly_ different pages. The following three images from the CSS Zen Garden website **all contain exactly the same HTML**, but look at how differently they present it:

***First example:***
![CSS Zen Garden 1](https://curriculum-content.s3.amazonaws.com/fewds-css/introduction-to-css/zengarden1.png "A long-scrolling single-page CSS Zen Garden design")

***Second example:***
![CSS Zen Garden 2](https://curriculum-content.s3.amazonaws.com/fewds-css/introduction-to-css/zengarden2.png "An animated CSS, full-screen browser single-page style Zen Garden design")

***Third example:***
![CSS Zen Garden 3](https://curriculum-content.s3.amazonaws.com/fewds-css/introduction-to-css/zengarden3.png "Blog-like CSS Zen Garden designs")

Like we said: all the difference between these images is created by CSS!
Astounding, right!?

We know now what CSS is and its purpose, so how does it differ from HTML and
how can we use it?

## Recognize The Differences Between HTML And CSS

HTML and CSS play two different roles. When we write HTML, we focus on
structure, hierarchy, and meaning &mdash; the "marking-up" of content.
Questions in the mind of an HTML author are:

* *Is it best to list these members' names with numbers, or bullets?*
* *Does this menu belong in in the navigation in the header?*
* *Should this additional reference be an aside, or a separate section?*

These questions deal with structure, hierarchy, and meaning, which are
are concerns of the content layer (HTML).

When defining the presentation layer (CSS), here are the questions we ask
ourselves:

* *Do we want the header menu to be stationary, or does it scroll with the
  browser window?*
* *How do we want the content to display inside of a container? For example,
  does it fill the whole area, edge-to-edge? Is there white space around
  the content and/or the container?*
* *How large should an `H1` be relative to an `H2`? What about an `H3`?
* *What properties should links have? Underline or no underline?*
  Which color for the normal state versus the hover state? Should the
  visited link state be different?*
* *How should the content appear when on a desktop machine versus a
  mobile device?*

As you ask yourself these questions, your focus is on the *aesthetic* quality
of the page. For each bit of _content_ we can define a _presentation rule_
that will change the way the HTML is displayed.

## The Principles Underlying CSS

For each _presentation rule_, there are 3 things to keep in mind:

1. What is the specific HTML we want to style?
2. What are the qualities we want to modify (e.g. the properties of text
   in a paragraph)?
3. _How_ do we want to modify the qualities of the element (e.g. font
   family, font color, font size, line height, letter spacing etc.)?

Once you've decided what to modify and how, we can start writing CSS rules.

CSS selectors are a way of declaring which HTML elements you wish to style.
Selectors can appear a few different ways:

- The type of HTML element(`h1`, `p`, `div`, etc.)
- The value of an element's `id` or `class` (`<p id='idvalue'></p>`, `<p
  class='classname'></p>`)
- The value of an element's attributes (`value="hello"`)
- The element's relationship with surrounding elements (a `p` within an element
  with class of `.infobox`)

For example if you want the body of the page to have a black background, your
selector syntax may be `html` or `body`. For anchors, you selector would be
`a`. A few more examples are listed below:

```css
/*
The CSS comment syntax is text between "slash-star" and "star-slash"
*/

/*
selects all anchor tag elements in the document (e.g. <a href="page-link.html">Page Link</a>)
*/
a

/*
selects all headers of type h3 in the document (e.g. <h3>Type selectors</h3>)
*/
h3

/*
selects all paragraph elements in the document (e.g. <p>Type selectors are used
to...</p>)
*/
p
```

[Type selectors documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors)

The element type `class` is a commonly used selector. Class selectors are used
to **select all elements that share a given class name**. The class selector
syntax is: `.classname`. Prefix the class name with a '.'(period).

```css
/*
select all elements that have the 'important-topic' classname (e.g. <h1 class='important-topic'>
and <h1 class='important-topic'>)
*/
.important-topic

/*
select all elements that have the 'welcome-message' classname (e.g. <p class='helpful-hint'>
and <p class='helpful-hint'>)
*/
.helpful-hint
```

You can also use the `id` selector to style elements. However, **there should
be only one element with a given id** in an HTML document. This can make
styling with the ID selector ideal for one-off styles. The `id` selector syntax
is: `#idvalue`. Prefix the id attribute of an element with a `#` (which is
called "octothorpe," "pound sign", or "hashtag").

```css
/*
selects the HTML element with the id 'main-header' (e.g. <h1 id='main-header'>)
*/
#main-header

/*
selects the HTML element with the id 'welcome-message' (e.g. <p id='welcome-message'>)
*/
#welcome-message
```

[id selectors documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors)


## Declaring CSS Properties and Values

Each element has a list of qualities that can be styled.  CSS "property" names
identify those qualities. For text styling, examples of property names include
text `color`, `text-align` and `line-height`.

CSS Property Values are directly related to property names. If we are working
with the `color` property, the value could be a named color such as `red`, or
`#660000`. Some properties have their values set with words, others with
numbers, and some can take both.

A CSS property name with a CSS property value is a **CSS declaration**.
To apply a CSS declaration like `color: blue` to a specific HTML
element, you need to combine your CSS declaration with a CSS selector. The
association between one or more CSS declarations and a CSS selector is called a
**CSS declaration block**. CSS declarations (one or more) that applied to a
specific selector are wrapped by curly braces (`{ }`).  Each declaration inside
a declaration block **must** be separated by a semi-colon (`;`).

Below is a sample CSS declaration block.

```css
selector {
  color: blue;
}
/*
This is a css declaration for a selector
'color' is a property name and 'blue' is a css property value
!!!!! CSS declarations must end with a semi-colon (;) !!!!!
*/
```

Let's write a more complete example declaration block.

```css
/*
The CSS declaration block below:
* Will apply to all `h1` elements
* Will change the text color to blue
* Will set the font family to Georgia
*/
h1 {
  color: blue;
  font-family: Georgia;
}
```

## Your Turn!

There is a simple HTML file in this directory - index.html. Start by looking at it in a browser - File-Open, navigate to this directory and select the `index.html`.

OK, so it's a valid HTML file, but it isn't very attractive. We've already created a CSS file in the same directory that it links to. Open that `styles.css` in a text editor. You'll see that there is a single style within it, but it has been commented out. Remove the comments, save the `styles.css` and reload the `index.html` in your browser. You should see the `h1` (the main title) turn from black to blue. Congratulations! You've just started to style a web page using CSS!

Now try to:
* Make the `h2` text bold
* Make the `h2` text bigger
* Add an `id` to the `h1` tag to uniquely identify it, and make the color of the `h1` red using the `id` tag
* Add a `class` to all of the bullets and use that to put a border round them (the css to do that is `border: 1px solid;`)

For extra credit, find some other [CSS properties](https://www.w3schools.com/html/html_css.asp) and practice applying them to various elements in your page.

## Summary

For web scraping, you're primarily going to be focused on the HTML that you want to reference to retrieve information from the web page, but it is good to at least know what CSS is, so you'll recognize it when you come across it. The selectors used by CSS to identify what HTML to mark up are also a useful introduction to the process of selecting elements within an HTML file - something you'll be learning to do. 
