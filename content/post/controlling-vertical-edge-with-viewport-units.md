---
title: "Controlling Vertical Edge With Viewport Units"
date: 2017-10-26T16:47:49-07:00
draft: false
---

Viewport units is a way to control the sizing of elements by allowing the browser to determine how wide or tall they are based on the users total area being displayed on their browser screen.

We can use vh for viewport height and vw for viewport width wherever we would use em, rem, %, or px.

One technique this is useful for is a split screen type of layout.

<pre class="code">
<code>
 &lt;!-- html code --&gt;
 &lt;article&gt;
   &lt;img src="landscape.jpg" alt="Rock Landscape"&gt; <br>
   &lt;div class="container"&gt;
   &lt;h1&gt;Rock Landscape&lt;/h1&gt;
   &lt;p&gt;Ne voluptua conclusionemque usu. His an prima ridens, ea ius iuvaret laoreet, ius eleifend repudiandae ut. Fugit lobortis an mea, et laoreet admodum oporteat mel. Sed sonet indoctum id, eam nostrum cotidieque persequeris an.&lt;/p&gt;
   &lt;/div&gt;
 &lt;/article&gt;

 /* css code */
 img {
     float: left;
     margin-right: 2em;
     width: 50%;
 }
</code>
</pre>

<article style="clear: both;">
   <img src="/blog/images/landscape.jpg" alt="Rock Landscape" style="float: left;
     margin-right: 2em;
     width: 50%;"> <br>
   <div class="container">
   <h1>Rock Landscape</h1>
   <p>Ne voluptua conclusionemque usu. His an prima ridens, ea ius iuvaret laoreet, ius eleifend repudiandae ut. Fugit lobortis an mea, et laoreet admodum oporteat mel. Sed sonet indoctum id, eam nostrum cotidieque persequeris an.</p>
   </div>
 </article>

<p style="clear: both;">
 Without viewport units resizing our window height will not allow the entire image to appear within the users viewport.

 Now lets give our image a height with some vh units instead of a width of 50%.
 </p>

<pre class="code">
<code>
 &lt;!-- html code --&gt;
 &lt;article&gt;
   &lt;img src="landscape.jpg" alt="Rock Landscape"&gt; <br>
   &lt;div class="container"&gt;
   &lt;h1&gt;Rock Landscape&lt;/h1&gt;
   &lt;p&gt;Ne voluptua conclusionemque usu. His an prima ridens, ea ius iuvaret laoreet, ius eleifend repudiandae ut. Fugit lobortis an mea, et laoreet admodum oporteat mel. Sed sonet indoctum id, eam nostrum cotidieque persequeris an.&lt;/p&gt;
   &lt;/div&gt;
 &lt;/article&gt;

 /* css code */
 img {
     float: left;
     margin-right: 2em;
     height: 100vh;
 }
</code>
</pre>

<article>
   <img src="/blog/images/landscape.jpg" alt="Rock Landscape" style="float: left;
     margin-right: 2em;
     height: 100vh;"> <br>
   <div class="container">
   <h1>Rock Landscape</h1>
   <p>Ne voluptua conclusionemque usu. His an prima ridens, ea ius iuvaret laoreet, ius eleifend repudiandae ut. Fugit lobortis an mea, et laoreet admodum oporteat mel. Sed sonet indoctum id, eam nostrum cotidieque persequeris an.</p>
   </div>
 </article>

<p style="clear: both;">
Giving our image a height of 100vh means that we want the image to appear 100% of the users viewport regardless of how tall they make their browser window.
 </p>