---
title: "CSS Shapes: Ellipse"
date: 2017-10-23T11:31:18-07:00
draft: false
---
## CSS Shapes
CSS shapes allow floated images to have text flow around it based on the shape of the image.

First lets start with some simple HTML:
<pre class="code">
<code>
 &lt;h1&gt;Duckrs The Duck&lt;/h1&gt;
 &lt;img src="duck.jpg" alt="Duckrs The Duck"&gt;
 &lt;p&gt;Phasellus ipsum libero, feugiat nec ex vel, sollicitudin laoreet justo. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Mauris sed mauris sapien. Sed ac sagittis odio. Nullam facilisis at urna nec semper. Integer pulvinar semper erat, eu blandit magna dapibus sollicitudin. Proin nec iaculis risus. Ut tristique eros sapien.&lt;/p&gt;
</code>
</pre>

Here's what the flow of text would look like without CSS shapes:
<pre class="code">
<code>
 img {
     float: left;
     margin-right: 2em;
     margin-bottom: 0.5em;
     border-radius: 50%;
 }
</code>
</pre>
### Duckrs The Duck

<img src="/blog/images/duck.jpg" alt="Duckrs The Duck" width="320" style="float: left;
     margin-right: 2em;
     margin-bottom: 0.5em;
     border-radius: 50%;">

Phasellus ipsum libero, feugiat nec ex vel, sollicitudin laoreet justo. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Mauris sed mauris sapien. Sed ac sagittis odio. Nullam facilisis at urna nec semper. Integer pulvinar semper erat, eu blandit magna dapibus sollicitudin. Proin nec iaculis risus. Ut tristique eros sapien.

With CSS shapes we can manipulate how the text flows around the image. Here we are using the ellipse value for the shape-outside property :
<pre class="code">
<code>
 img {
     float: left;
     margin-right: 2em;
     margin-bottom: 0.5em;
     border-radius: 50%;
     shape-outside: ellipse(45% 45%);
 }
</code>
</pre>

### Duckrs The Duck

<img src="/blog/images/duck.jpg" alt="Duckrs The Duck" width="320" style="float: left;
     margin-right: 2em;
     margin-bottom: 0.5em;
     border-radius: 50%;
     shape-outside: ellipse(45% 45%);">

Phasellus ipsum libero, feugiat nec ex vel, sollicitudin laoreet justo. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Mauris sed mauris sapien. Sed ac sagittis odio. Nullam facilisis at urna nec semper. Integer pulvinar semper erat, eu blandit magna dapibus sollicitudin. Proin nec iaculis risus. Ut tristique eros sapien.

You can find out more about CSS shapes [by heading over to the w3c website](https://www.w3.org/TR/css-shapes-1/#funcdef-ellipse).