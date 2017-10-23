---
title: "How HTML, CSS, and JavaScript Work Together"
date: 2017-10-21T20:35:11-07:00
draft: false
---
## HTML

Hypertext Markup Language gives structure and meaning to a page.
<pre class="code">
<code>
 &lt;button&gt;This is a button in HTML.&lt;/button&gt;
</code>
</pre>

The above code will render as:
<pre class="code">
    <button>This is a button in HTML.</button>
</pre>

## CSS

Cascading Style Sheets are text documents with rules that describe how the elements in HTML documents should be displayed.
<pre class="code">
<code>
 button {
   color: red;
 }
</code>
</pre>

Adding this line of code to our HTML file will render all text in button elements with the color red.
<pre class="code">
    <button style="color: red;">This is a button in HTML.</button>
</pre>

## JavaScript

JavaScript allows users to ineract with the page by adding behavior.
<pre class="code">
<code>
 const button = document.querySelector('button');

 const changeText = () => {
  button.innerText = "Hello World!";
 }

 button.addEventListener('click', changeText);
</code>
</pre>

This will let our button run the changeText function once it has been clicked.
<pre class="code">
    <button class="ex-js" style="color: red;">This is a button in HTML.</button>
</pre>