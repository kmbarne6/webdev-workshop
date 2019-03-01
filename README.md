# Intro to Web Development

Despite the complexity of modern JavaScript web development frameworks, there's still quite a bit that can be accomplished using simple HTML and CSS.  In this workshop, we'll be taking a look at some of the basics of both to see how you can put together simple websites.

## What are HTML and CSS?

**H**yper**T**ext **M**arkup **L**anguage is a language that is used to mark up, or format, plain text into pages that have some actual structure.  On its own, HTML only lets you build static pages (that is, a page that appears the same to every user), but it can still be used to give structure and formatting to text.  HTML is the foundational technology that underlies all of the rest of the World Wide Web.  There are various different HTML tags, which represent the different elements that you might see on a page, and they can be nested inside of each other to give the page the structure that you desire.  

**C**ascading **S**tyle **S**heets is a language that is used to give more interesting styling to HTML pages, and allows the content of the HTML page itself to be separated from the way that it is displayed.  This makes pages more attractive and can give multiple pages a unified formatting.

Web browsers will _render_ pages written in HTML and CSS, using the HTML tags to give your text _structure_, and the CSS tags to give your page _style_.

The good news for writing HTML is that most web browsers have a philosophy of "it's better to display something broken than to display nothing at all".  This means that even if you mess up your HTML, your browser will still display _something_ that you can see and attempt to figure out where you've gone wrong.

## A Simple Example
Take a look at [Example 1](examples/1/1.html) for an example of a simple HTML page.  We encourage that you open it up in your web brower (Firefox, Internet Explorer, Chrome, Safari) so that you can see the rendered version, as well as a rich text editor (Notepad++, Visual Studio Code, vim, or the like) so that you can see the source of the page itself.  

There's a bunch going on in that page, so let's take it line-by-line.

The `<html>` element is the _root element_ for the page.  Remember how HTML elements can be nested inside of each other?  This is the outermost element, inside of which everything else is nested.  We need this tag to tell your browser that this is a HTML page, so that it knows how to render things.  By the way, see the `</html>` tag at the very end?  Most HTML elements have a **start tag**, and an **end tag**.  This is necessary to tell the browser where each tag begins and where it ends, so that it can handle the proper nesting of elements.  

The `<head>` tag starts the _head_ of the page, which contains meta-information about the page.  This can include links to stylesheets (more on that later!) and other content that impacts the entire page.

The `<title>` tag defines the _title_ of the page, which is what shows up as the name of the page in your browser's tab.  Make sure you remember to close it with the `</title>` tag at the end!

The `<body>` tag defines the part of the page that is actually visible to a user -- it's only the content that lies between the `<body>` and `</body>` tags that is rendered for a user of the computer to actually see.

The `<h1>` tag defines a _heading_, or section on the page, and uses large text to make it stand out.  HTML supports six different _heading_ tags, `<h1>` through `<h6>` for different levels of headings.  `<h1>` is the largest, and `<h6>` is the smallest.

The `<p>` tag defines a _paragraph_--this is where most of the text on a HTML page actually goes.

Remember to close off your page at the end with a `</body>` and a `</html>` tag!

Notice that we have the example _indented_ with spaces used to nest each element visibly "inside" of its parent element.  This is not strictly necessary, and the browser's parser will handle the page fine without it, but it makes it much easier to look at the page and intuitively know what it will look like.


**Activity**

Now that you've seen the basics of HTML structuring, see if you can add another large heading, and a smaller heading with some text under it.  If you get stuck, you can take a look [here](examples/1/1-sln.html) for a hint.


## Links and Images
That was all well and good, but we usually want to have web pages that include more than just text on them.  Fortunately, HTML makes it easy to include _links_ that go between multiple different pages, so that a user can easily go from one page to the next.  

Before we see how links and images work, however, we need to introduce a new concept: _attributes_.  All HTML elements can have attributes, which get attached to the start tag, and provide more information about the element.  _Attributes_ are what HTML uses to make links and images work properly.

Take a look at [Example 2](examples/2/2.html) for a HTML page that includes both a link and two included images.

Let's unpack this new page line-by-line to see what makes it work:

`<a>` is HTML's _anchor_ tag, which is used to create links.  The `href` attribute on the tag specifies the _destination_ of the link -- where the user will be sent when they click on it.  The link text, or anything else that you want to be clickable, goes between the closing `>` of the start tag and the opening `<` of the end tag.

The next thing you'll see that's new is the `<br>` tag.  This is a _break_ tag, which tells HTML to insert a linebreak (or new line) before the next element.  By default, HTML ignores all linebreaks in your text, so this is necessary to make elements show up on separate lines.

Third, you'll see the `<img>` tag.  This is HTML's _image_ tag, which is used to include images on a page.  Like the _anchor_ tag above, it also needs an attribute -- the source of the image to display.  This is specified through the `src` attribute.  Note that the source of the image can either be a local (relative) path (as in the first example) or an _absolute_ path, as in the second.

You'll also see in the second `<img>` tag we have another attribute -- `width`.  This is used to set a width for the image, overriding image's actual size, which scales it down to make it fit in the page better.

**Activity**

Now that you know how images and links work, see if you can combine them.  Make a link on your page that goes to Wikipedia's [page about moose](https://en.wikipedia.org/wiki/Moose), but instead of having a text link to click on, include the picture of the moose instead!

If you get stuck, you can look [here](examples/2/2-sln.html) for a hint.


## Lists

Sometimes when building a page, we want the ability to create lists of related elements.  HTML supports two different types of lists.  We'll take a look at each one in turn.  You can see both of them in [Example 3](examples/3/3.html).

_Ordered lists_, as you would expect from the name, have order.  These lists make most sense when the items being displayed have an _intrinsic ranking_.  An ordered list starts with the `<ol>` tag, and as you'd expect by now, ends with the `</ol>` tag.

By default, elements in HTML ordered lists are _numbered_, starting at 1, but you can specify a different list type with the `type` attribute.  The various types supported are shown below:

|Type | Description |
|-----|-------------|
|`type="1"`|Elements in the list are labeled with numbers (default behavior)|
|`type="A"`|Elements in the list are labeled with uppercase letters|
|`type="a"`|Elements in the list are labeled with lowercase letters|
|`type="I"`|Elements in the list are labeled with lowercase Roman numerals|


_Unordered lists_ don't rank elements, but instead display them using bullet points or similar.  Naturally, they make sense when the elements being displayed _do not_ have any intrinsic order.  Unordered lists start with a `<ul>` tag and end with `</ul>`.  We'll see how you can style your unordered lists using CSS later on.

Both ordered lists and unordered lists use the same tag, `<li>`, to denote an element in the list.

**Activity**

Although it can get a bit messy, it's possible to nest lists inside of lists.  See if you can create an ordered list of at least three elements that has another ordered list nested inside of one element.  Try using a different style for each of the lists!

If you get stuck, you can look [here](examples/3/3-sln.html) for a hint.

## Tables
Often when presenting information, being able to use tables is very handy.  Fortunately, HTML has easy support for this as well.  [Example 4](examples/4/4.html) shows how to write tables in HTML.  Tables are handled in _row-major order_; we write them one row at a time, and cells go inside of each row element.

Let's unpack this example one piece at a time:
`<table>` is the HTML tag that defines a table.  Just using this alone creates an empty table with nothing inside of it, but we can start nesting our desired elements within it.

`<tr>` defines a _table row_ that stretches horizontally from left to right across the screen.  Note that this _still_ doesn't actually create any elements in the table, just defines a structure where we can actually place them.

`<td>` defines a _table cell_.  This is the unit that is actually displayed on the page.  Cells flow from left to right within a row, and are stacked vertically into _columns_.  

Note that in our previous example, we made sure that we have the same number of cells on each row.  This, however, is not required; when the page gets rendered, the number of columns that show up is equal to the _maximum number in any row_.  So, as you can see in [Example 4B](examples/4/4b.html), the browser will display _three_ columns because of the three `<td>` elements in the last row.

It's also possible to group multiple cells in a table together into a single, larger cell.  This is done with the `colspan` attribute when you want the grouping to span across multiple columns, or `rowspan` attribute if you want it to span across multiple rows.

**Activity**

Create a table that has a cell which spans across two columns or two rows.

If you get stuck, you can look [here](examples/4/4-sln.html) for a hint.


## CSS
So far, we've learned how to create some simple webpages using HTML, but all of the pages that we've created are pretty plain.  We've learned how to structure the test in increasingly interesting ways, but it's all thus far been black text on a white background.  CSS lets us fix this -- we can define _stylesheets_ that impact how information gets displayed on a page.  While [there are libraries](https://getbootstrap.com/docs/3.4/css/) that handle this, today we'll be learning how to write some of the basics from scratch.

To add CSS styling to a HTML page, we encourage you to use an _external style sheet_.  This means that the styling is not inlined within a specific HTML page or element, and can thus be shared among multiple different pages, promoting code reuse and making it easy to create a uniform experience.  There are two required parts:

* A `<link rel="stylesheet" type="text/css" href="style.css">` tag nested between the `<head>` and `</head>` tags.  This _links_ the stylesheet to this HTML page so that its rules will be applied to the current page.
* A _stylesheet_ which contains the CSS rules to be applied.  We'll go into more detail on this in a moment.

Take a look at [Example 5 HTML](examples/5/5.html) and [Example 5 CSS](examples/5/style.css) for an example HTML page and corresponding stylesheet.  Let's walk through this line-by-line 

In the HTML page, the `<link rel="stylesheet" type="text/css" href="style.css">` specifies that we have a link to an external CSS file, named `style.css`.  The other attributes specify the type of this file so that the browser knows how to parse it correctly.

In the CSS file, we have three largely similar groups.  Each of these is a CSS _rule_, which consists of a _selector_ (the `body` selector says that this applies to the entire `body` of the page, the `h1` says that this applies to all `<h1>` elements) and a _declaration_, which says what styling is going to be applied to that element.  For instance, for the `body` selector, we have the `background-color: orange;` declaration, which says that we'll make the background of the entire page orange.

As you can see from this example, it's possible to apply multiple _declarations_ to a given selector: we say that all `<h1>` elements will be coloured green, and have a border surrounding them.

The rules that we've seen so far make it pretty easy to apply a set of rules to _all_ elements of a certain type (for instance, all `<h1>` elements).  This, however, is not very flexible: in order to get the styling we want for a page, it's often better to apply styling only to a _subset_ of elements (or, perhaps, apply the same styling to elements of different types).  Fortunately, HTML _attributes_ let us handle this.

In [Example 5B](examples/5/5b.html) we define HTML elements that have a `class` attribute which lets us tune our CSS more precisely.  Then, in our [associated CSS file](examples/5/style5b.css), we use a period (`.`) and the name of the class to select all of the elements with that matching class.  This lets us make _some_ of the elements on our page blue, even though they share different element types.

What if we want to colour just a single element?  That's easy, too: we can define an `id` for that element, and use the corresponding pound symbol selector (`#`) to apply CSS rules just to it.  That's how we can colour just a single element.

There are many other things that we can do with CSS other than just colouring certain elements.  In Example 5 ([HTML](examples/5/5c.html) and [CSS](examples/5/style5c.css)) we use CSS to add a visible border around table elements, and some padding so that everything isn't so compressed together.  Remember, the `table` selector means that the first rule applies to the entire table, while the `td` selector means that pair of rules applies only to the cells within the table.

Perhaps most interestingly, we can also use CSS to give elements _conditional properties_ -- that is, properties that only show up when a user takes a certain action.  In our example, we've used the `:hover` attribute to make our links show up in green while the user's mouse hovers over them, and in red while the link is being actively clicked.  Logic like this can make websites much more dynamic, with relatively little programming effort, as they "respond" to where a user points their mouse.

## Putting it all together

By now, you've seen how it's possible to put together simple webpages using a variety of HTML structures, and style elements using CSS.  Where you take this is up to you, but for practice, try building a simpleweb page that serves as a resume, focusing on your educational experience and programming expertise!