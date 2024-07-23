# Single Page Site Starter

This repo contains starter code for building your single page web site. 

The code here is shown in stages that walk through the process you might follow to if you were building a single page site from scratch. 

While you can build the example project, its better to swap the content here for content of your own, using this work as a template for a single page site of your own design! 

# Step 0 - index-0.html

The first step is define a subject and content, then divide the content into sections. 

For the subject you can think about your single page site similar to writing an essay. You'll have an introduction, supporting topics, and a conclusion, each of these is a section. 

The difference between the web site and and essay is the website will have pictures and be lighter on text content. 

In [inde-0.html](index-0.html) I've used the boilderplate HTML code along with a series of sectional tags to outline the content. 

```HTML
<main>
  <nav id="nav"></nav>
  <section id="banner"></section>
  <section id="topic-1"></section>
  <section id="topic-2"></section>
  <section id="topic-3"></section>
  <footer id="contact"></footer>
</main>
```

# Step 1 - index-1.html

In this stage I've added content and structure to each section. 

Important! Every section should have a heading! You'll always use headings in order. The top level heading is h1, if this topic has a sub section it will use an h2 heading, and so on. Never choose a heading bcause of the font size! You can always set the font size with CSS. 

Notice each section contains a heading (h1 to h6) and some other content, like p or ul etc. 

```HTML
<section id="banner">
  <!-- Section title and heading -->
  <h2>Name of Section</h2>
  <!-- Section content expand this with anythings -->
  <p>Some Text...</p>
</section>

<section id="topic-1">
  <!-- A section heading -->
  <h1>Topic 1</h1>
  <!-- A section might contain a list -->
  <ul>
    <li></li>
    <li></li>
    <li></li>
  </ul>
</section>
```

This might seem a little abstract at this point, since there is no content yet. Use your imagination. Imagine the p contains an interesting paragraph of text and the heading above labels this paragraph section. 

Imagine `topic-1` is a list of of important points and the heading above it names that list. 

Notice that the headings (`h1`, `h2`, etc.) always appear inside the `section` they are labeling. This is important because, placing the heading inside a section associates the heading with that section!

# Step 2 - index-2.html

This step adds a few styles to get the page to display as a series of sections in a single scrolling page. 

Notice the styles exist inside a `<style>` tag. The `style` tag contains code written in the CSS language. 

CSS is written in rules. Every rule has a selector followed by a list of properties and values. 

The rule below uses the "type" selector to select the `body` tag. A selector "selects" elements in the document. The rule applies the values to the properties of the elements selected. In the example below, the property is `margin` and the value is `0`. So this rule sets the `margin` of the `body` tag to a value of `0`.

```CSS
body {
  margin: 0;
}
```

The selecto below, `nav, main > section`, use some extra character to perform a more complex selection. The `,` (comma) is the group selector, it selects two or more groups of selectors. The `>` (greater than) is the child selector, it selects child element, in this case its looking for `section` tags that children of `main`. The whole selector here selects the `nav` tag, and any `section` tags that children of `main`.

```CSS
nav, main > section {
  overflow: auto;
}
```

This block removes the default margin from the body element. Without this you'll a small gap around the edge and your content won't reach the edge of the page. 

Margins on elements like `h1` and `p` extend outside their containers. This creates gaps between sections. This rule removes those gaps. Try commenting this out and viewing the code in the browser. 

```CSS
main > section {
  min-height: 100vh;
}
```

I wanted each section to be as least as tall as the size of the window. This rule says the minimum height should be 100% of the view height (height of the window). 

`vh` is a unit that represents a percentage of the browser windows vertical size. `100vh` is `100%` the height of the window, `50vh` would be 50% as tall as the window.

The two selectors below use the `#` to select elements by their `id` name. Find the element with `id="nav"` and `id="banner"`. 

```CSS
#nav {
  background-color: #FF3B30;
}

#banner {
  background-color: #26B63E;
}

...
```

These rules apply to each content section through the unique ids assigned to each. Here a different  background color was applied to each section to make them standout. 

# Step 3 - index-3.html

This step takes look at the nav bar. I added some real content and renamed the links and ids for the sections. 

To divide the nav bar into two parts ocupying opposite sides you need two child elements. 

```CSS
#nav {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  ...
}
```

Here I used `align-item: basline` to align all elements on the baseline. This way all of the text "sits" on the same line. 

In the example the right side of the nav is a ul with four items. Use flex again to align these list items in a row. 

```CSS
nav ul {
  display: flex;
  list-style: none;
}
```

The links should have a little more space. 

```CSS
nav ul a {
  padding: 1em;
}
```

# Step 4 - index-4.html

In this step you'll look at one section with a background image and some text content in the center. 

I renamed the ids so they made more sense to the subject of content. Here I'm going to style a section on Raymond Scott, you should look him up he created some very interesting music you migth recognize. 

The idea is to fill this section with a background image. 

I found some images searching the with Google. I made sure to choose an image that was at least 1200px wide if I could find one. If not use what you can get. 

I put my images in a folder named: `images`.

Set the id of the first section to #raymond-scott. 

Then I used these styles to make the image fill this section. 

```CSS
#raymond-scott {
  background-color: #26B63E;
  background-image: url(images/scott-1.jpg);
  background-size: cover;
}
```

Using `background-size: cover;` here makes the image fill the space and bleed off the edges. 

My section had heading and some other text. I wrapped the heading and text in a div tag so I could move them as a group. 

```HTML
<section id="raymond-scott">
  <div>
    <h2>Raymond Scott</h2>
    <p>Some Text...</p>
  </div>
</section>
```

The div a block tag, that has no semantic meaning. We use it to do computer stuff without saying anything about the content. 

```CSS
#raymond-scott {
  ...

  display: flex;
  justify-content: center;
  align-items: center;
}
```

Center the children with flex. 

```CSS
#raymond-scott {
  ...

  ...

  font-size: 4em;
  color: #fff;
}
```

I wanted the text be big and visible. Choose a color that constrasts with the background image. 

```CSS
#raymond-scott h2, #raymond-scott p {
  margin: 0;
  text-shadow: 0 0 20px #000000;
}
```

To reduce the space between h2 and p tags remove the margin. 

The Text shadow migth help add some visual separation with the text and the background image. 

I wanted to push the content a little down and the to the right. 

```CSS
#raymond-scott > div {
  position: relative;
  left: -120px;
  top: 120px;
}
```

Setting `position: relative;` allows the element to be moved, `left: -120px;` moves the image 120px to the left, a positive number would move to the right, `top: 120px;` moves the image down.  

# Step 5 - index-5.html

This next section displays three cards side by side. 

Each card uses the following markup. This is what I used. 

I started with a list. 

```HTML
<ul>
  <li class="card"></li>
  <li class="card"></li>
  <li class="card"></li>
</ul>
```

Each list item `<li>` will be a card. The class name will help since not all list items will be cards. Using the class will allows to apply the card style to anything with the card class. 

Each list item looked like this: 

```HTML
<li class="card">
  <img src="images/moog-0.jpg">
  <h3>Bob Moog</h3>
  <p>The inovator...</p>
</li>
```

_Notice the paths! paths in CSS are always relative to the stylesheet!_ 

Remove the list default styles. 

```CSS 
#robert-moog ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
```

Now use flex to arrange the list items in a row. 

```CSS 
#robert-moog ul {
  ...

  display: flex;
  justify-content: center;
}
```

Define some card styles: 

```CSS
.card {
  width: 400px;
  margin: 1em;
  background-color: #eee;
}
```

Make the image fit the width of the card: 

```CSS
.card img {
  width: 100%;
}
```

# Step 6 - index-6.html

Here I wanted to make a content box that was 75% the width of the container but also not wider than 700px. If the lines of text are too wide it becomes hard to read. 

```CSS
#wendy-carlos > div {
  background-color:rgba(255, 255, 255, 0.44);
  padding: 1em;
  width: 75%;
  max-width: 700px;
}
```

The `background-color:rgba(255, 255, 255, 0.44);` is  a transparent white. The last value is the transparency. 

# Step 7 - index-7.html

This time arrange two elements side by side and set the proportional width of each. 

Set the background and flex.

```CSS
#suzanne-ciani {
  background-color: #461c3b;
  display: flex;
  color: #fff;
  background-image: url(images/sound-texture.jpg);
  background-size: cover;
}
```

Make the container 75% the width of the page. 

```CSS
#suzanne-ciani > div {
  display: flex;
  justify-content: center;
  width: 75%;
  margin: auto;
}
```

There are two children. One is an image the other has some text. 

```CSS
#suzanne-ciani > div > div:nth-child(1) {
  flex: 3;
  margin: 0 2em 0 0;
}

#suzanne-ciani > div > div:nth-child(2) {
  flex: 2;
}
```

Setting the flex property sets what proportion that element fills. Here the first element takes up 3 parts, and the second takes 2. So first takes up 3/5 or 60% and the second takes 2/5 or 40%.


# Step 8 - index-8.html

Time to look at the form. Forms have lots of details that need style attention. 

This is the structure I used for the inputs. 

```HTML
<label>
  <span>Name</span>
  <input type="text">
</label>
```

By putting the text of the label in a `<span>` tag I can target and style the label text seprately from the label as a whole which contains the text and the input. 

To arrange the text above the input use flex and direction column.

```CSS
#contact label {
  display: flex;
  flex-direction: column;
}
```

The inputs and text area should look the same. Might as well style both. Adding some padding will push the edge of the box away from the text that is input. 

Be sure to style the border. 

```CSS
input, textarea {
  border: 1px solid #000;
  padding: 0.5em;
  margin: 0 2em 0 0;
  width: 20em;
  font-size: 1em;
}
```

The teaxtarea is a multiline input setting the height in em will let you set the height to display a number of full lines. 

```CSS
textarea {
  height: 9em;
  margin: 0 0 0 0;
}
```

Using the box model, the teaxtarea should display 8 lines. That's height 9em, with padding of 0.5em. 

The submit button. 

```CSS
form button {
  width: auto;
  font-size: 1em;
  margin: 1em 0;
  align-self: flex-end;
  padding: 0.5em 1em;
  background-color:rgb(0, 0, 0);
  color: #fff;
  border: none;
}
```

The default button style adds a background and border. Be sure to style thesde. Give the button a contrasting color to make stand apart. You want people to see the button and know they can click it. 

# Step 9 - index-9.html
This step adds some JavaScript to the page. In this case I added the AOS (Animate On Scroll) library. This some code that applies animations to elements that are applied when those elements scroll into view. 

Read about AOS and see a demo here: https://michalsnik.github.io/aos/

The first step is to import the library. You can link to local files or remote files stored on CDN (Content Delivery Network). I used the second option. 

Add the following to the `<head>` tag: 

```HTML
<link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
```

This links to CSS styles required for AOS. 

Then add the following to the bottom of the `<body>` tag, before the closing tag `</body>`!.

```HTML
<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
```

You can find these links near the bottom of the AOS demo page. 

Why place the script at the bottom of the body tag? JS is run when the browser encounters the tag. If the tag were placed at the top of the page it's possible that some of the would not have loaded when the AOS was run. For AOS to work properly the page needs to be fully loaded before the AOS code is run. Placing the tag at the bottom of the means it loads after all of the other "tags". 

Below this script add another script: 

```HTML
<script>
  AOS.init();
</script>
```

This line of code initializes AOS. 

## Using AOS
AOS works through attributes you assign to tags. AOS scans the document for elements with attributes named: `data-aos`. It uses the value of these attributes to detemrine what type of animation to apply to that element. Scan the AOS demo page for examples. 

Scan the example for the attributes I used, find these: 

```HTML
<div data-aos="fade-up">
```

```HTML
<h2 data-aos="fade-right">Robert Moog</h2>
```

```HTML
<div data-aos="slide-right">
```

There are a few more. 

# Conclusion
This example shows the basics of creating a single page website. It uses HTML, CSS, and JS following principles and ideas used on almost every website you might visit. 

There is a lot more to learn but, these foundational ideas will appear everywhere! 

What did this cover: 
- HTML tags and semantic HTML
- CSS, including selectors, properties and values
- A range of CSS properties including: margin, width and height, font, flex, and more
- JavaScript, using the script tag, importing code from a CDN, and using the AOS library
