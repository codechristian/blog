---
title: "Controlling Vertical Edge With Viewport Units"
date: 2017-10-26T16:47:49-07:00
draft: false
---

Viewport units is a way to control the sizing of elements by allowing the browser to determine how wide or tall they are based on the users total area being displayed on their browser screen.

We can use vh for viewport height and vw for viewport width wherever we would use em, rem, %, or px.

One technique this is useful for is a split screen type of layout.

{{< highlight html >}}
<!-- html code -->
<article>
  <img src="landscape.jpg" alt="Rock Landscape"> 

  <div class="container">
  <h1>Rock Landscape</h1>
  <p>Ne voluptua conclusionemque usu. His an prima ridens, ea ius iuvaret laoreet, ius eleifend repudiandae ut.</p>
  </div>
</article>
{{< / highlight >}}

{{< highlight css>}}
/* css code */
img {
  float: left;
  margin-right: 2em;
  width: 50%;
}
{{< / highlight >}}

<article style="clear: both;">
   <img src="/blog/images/landscape.jpg" alt="Rock Landscape" style="float: left;
     margin-right: 2em;
     width: 50%;"> <br>
   <div class="container">
   <h1>Rock Landscape</h1>
   <p>Ne voluptua conclusionemque usu. His an prima ridens, ea ius iuvaret laoreet, ius eleifend repudiandae ut.</p>
   </div>
 </article>

<p style="clear: both;">
 Without viewport units resizing our window height will not allow the entire image to appear within the users viewport.

 Now lets give our image a height with some vh units instead of a width of 50%.
 </p>

{{< highlight html >}}
<!-- html code -->
<article>
  <img src="landscape.jpg" alt="Rock Landscape"> 

  <div class="container">
  <h1>Rock Landscape</h1>
  <p>Ne voluptua conclusionemque usu. His an prima ridens, ea ius iuvaret laoreet, ius eleifend repudiandae ut.</p>
  </div>
</article>
{{< / highlight >}}

{{< highlight css>}}
/* css code */
img {
  float: left;
  height: 100vh;
  margin-right: 2em;
}
{{< / highlight >}}

<article>
   <img src="/blog/images/landscape.jpg" alt="Rock Landscape" style="float: left;
     margin-right: 2em;
     height: 100vh;"> <br>
   <div class="container">
   <h1>Rock Landscape</h1>
   <p>Ne voluptua conclusionemque usu. His an prima ridens, ea ius iuvaret laoreet, ius eleifend repudiandae ut.</p>
   </div>
 </article>

<p style="clear: both;">
Giving our image a height of 100vh means that we want the image to appear in 100% of the users viewport regardless of how tall they make their browser window.
 </p>