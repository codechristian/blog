---
title: "Avoid Margin Collapse With These Techniques"
date: 2017-10-27T17:29:15-07:00
draft: false
---

Margin collapse is the default behavior when elements are right next to each other but sometimes we want to prevent this effect.

## margin-top or margin-bottom

Our first solution would be to exclusively use only <code class="code-key">margin-top</code> or <code class="code-key">margin-bottom</code> for spacing between elements.

{{< highlight html >}}
<!-- html code -->
<div class="box box1">box1</div>
<div class="box box2">box2</div>
<div class="box box3">box3</div>
{{< / highlight >}}

{{< highlight css >}}
/* css code */
.box {
  height: 100px;
  width: 200px;
  border: 1px solid black;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
} 

.box1 {
  background-color: orange;
  margin-bottom: 20px; /* add some spacing below box1 */
} 

.box2 {
  background-color: green;
  margin-bottom: 10px; /* add some spacing below box2 */
} 

.box3 {
  background-color: purple;
}
{{< / highlight >}}


<div style="display: flex; align-items:center;
flex-direction:column;">
  <div class="box1" style="height: 100px;
width: 200px;
background-color: orange;
border: 1px solid black;
color: white;
display:flex;
justify-content:center;
align-items: center;
margin-bottom: 20px;">
box1
</div>
<div class="box2" style="height: 100px;
width: 200px;
background-color: green;
border: 1px solid black;
color: white;
display:flex;
justify-content:center;
align-items: center;
margin-bottom: 10px;">
box2
</div>
<div class="box3" style="height: 100px;
width: 200px;
background-color: purple;
border: 1px solid black;
color: white;
display:flex;
justify-content:center;
align-items: center;">
box3
</div>
</div>

As a result of only using <code class="code-key">margin-bottom</code> to give some spacing between our three boxes we no longer have to worry about the complexity of margin collapse. 

We get exactly 20px below box1 and 10px below box2.

## Substitute margin for padding

This solution is usually a good one since padding does not have the effect of collapsing on elements.

{{< highlight html >}}
<!-- html code -->
<div class="box box1">box1</div>
<div class="box box2">box2</div>
<div class="box box3">box3</div>
{{< / highlight >}}

{{< highlight css >}}
/* css code */
.box {
  height: 100px;
  width: 200px;
  color: black;
  display: flex;
  justify-content: center;
  align-items: center;
} 

.box1 {
  padding: 60px 0; /* add some spacing above and below box2 */
} 

.box2 {
  background-color: green;
  border: 1px solid black;
  color: white;
} 

.box3 {
  padding: 40px 0; /* add some spacing above and below box3 */
}
{{< / highlight >}}

<div style="width: 200px; margin: 0 auto;">
<div class="box1" style="height: 100px;
width: 200px;
color: black;
display:flex;
justify-content:center;
align-items: center;
padding: 60px 0;">
box1
</div>
<div class="box2" style="height: 100px;
width: 200px;
background-color: green;
border: 1px solid black;
color: white;
display:flex;
justify-content:center;
align-items: center;
">
box2
</div>
<div class="box3" style="height: 100px;
width: 200px;
color: black;
padding: 40px 0;
display:flex;
justify-content:center;
align-items: center;">
box3
</div>
</div>

This works great in our example above since our box1 and box3 elements are not using the space taken up by padding for things such as background color or border style.

However once we do, padding does not work well to space out our elements as shown below.

{{< highlight html >}}
<!-- html code -->
<div class="box box1">box1</div>
<div class="box box2">box2</div>
<div class="box box3">box3</div>
{{< / highlight >}}

{{< highlight css >}}
/* css code */
.box {
  height: 100px;
  width: 200px;
  color: white;
  border: 1px solid black;
  display: flex;
  justify-content: center;
  align-items: center;
} 

.box1 {
  padding: 60px 0; /* add some spacing above and below box2 */
  background-color: orange;
} 

.box2 {
  background-color: green;
} 

.box3 {
  padding: 40px 0; /* add some spacing above and below box3 */
  background-color: purple;
}
{{< / highlight >}}

<div style="width: 200px; margin: 0 auto;">
<div class="box1" style="height: 100px;
width: 200px;
color: white;
border: 1px solid black;
background-color: orange;
display:flex;
justify-content:center;
align-items: center;
padding: 60px 0;">
box1
</div>
<div class="box2" style="height: 100px;
width: 200px;
background-color: green;
border: 1px solid black;
color: white;
display:flex;
justify-content:center;
align-items: center;
">
box2
</div>
<div class="box3" style="height: 100px;
width: 200px;
color: white;
border: 1px solid black;
background-color:purple;
padding: 40px 0;
display:flex;
justify-content:center;
align-items: center;">
box3
</div>
</div>

## Empty elements

In this last technique we can create an empty element in our html and give it some small amount of height in css.

We would then insert this empty element anyplace we want to prevent margin collapse.

{{< highlight html >}}
<!-- html code -->
<div class="box box1">box1</div>
<div class=“el-empty”></div>
<div class="box box2">box2</div>
<div class=“el-empty”></div>
<div class="box box3">box3</div>
{{< / highlight >}}

{{< highlight css >}}
/* css code */
.box {
  height: 100px;
  width: 200px;
  border: 1px solid black;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
} 

.box1 {
  background-color: orange;
  margin-bottom: 60px; /* add some spacing below box1 */
} 

.box2 {
  background-color: green;
  margin: 20px 0; /* add some spacing above and below box2 */
} 

.box3 {
  background-color: purple;
  margin-top: 40px; /* add some spacing above box3 */
}

.el-empty {
  height: 1px; /* give our empty div element some height */
}
{{< / highlight >}}

<div style="width: 200px; margin: 0 auto;">
<div class="box1" style="height: 100px;
width: 200px;
color: white;
border: 1px solid black;
background-color: orange;
display:flex;
justify-content:center;
align-items: center;
margin-bottom: 60px;">
box1
</div>
<div class="el-empty" style="height: 1px;"></div>
<div class="box2" style="height: 100px;
width: 200px;
background-color: green;
border: 1px solid black;
color: white;
margin: 20px 0;
display:flex;
justify-content:center;
align-items: center;
">
box2
</div>
<div class="el-empty" style="height: 1px;"></div>
<div class="box3" style="height: 100px;
width: 200px;
color: white;
border: 1px solid black;
background-color:purple;
margin-top: 40px;
display:flex;
justify-content:center;
align-items: center;">
box3
</div>
</div>

 Margin collapse between our elements is prevented with this method because it only takes effect for consecutive elements. Our inserted empty element causes seperation and takes on the margin from its surrounding elements.

In our example we mixed <code class="code-key">margin-bottom</code>, <code class="code-key">margin-top</code>, and just plain <code class="code-key">margin</code> in our css code and the result is what is usually desired. We can see that box2 has top and bottom margin of 20px and it does not dissapear even though box1 has bottom margin of 60px while box3 has top margin of 40px. 