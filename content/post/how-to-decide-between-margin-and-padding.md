---
title: "How To Decide Between Margin And Padding"
date: 2017-10-25T12:25:45-07:00
draft: false
---

The margin and padding css properties are usually used to give html elements some spacing.

## Margin

With margin the space is added outside of an elements border.

{{< highlight html >}}
<!-- html code -->
<div class="box box1">box1</div>
<div class="box box2">box2</div> 
{{< / highlight >}}

{{< highlight css>}}
/* css code */
.box {
  height: 100px;
  width: 200px;
  border: 1px solid black;
  color: white;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}

.box1 {
  background-color: orange;
} 

.box2 {
  background-color: green;
}
{{< / highlight >}}

Before adding margin our block elements stack right on top of each other.

<div style="display: flex; align-items:center;
flex-direction:column;">
<div class="box1" style="height: 100px;
   width: 200px;
   background-color: orange;
   border: 1px solid black;
   color: white;
   cursor: pointer;
   display:flex;
   justify-content:center;
   align-items: center;">
   box1
 </div>
 <div class="box2" style="height: 100px;
   width: 200px;
   background-color: green;
   border: 1px solid black;
   color: white;   
   cursor: pointer;
   display:flex;
   justify-content:center;
   align-items: center;">
   box2
 </div>
 </div>

Now lets add some margin below box1 and above box2.

{{< highlight html >}}
<!-- html code -->
<div class="box box1">box1</div>
<div class="box box2">box2</div> 
{{< / highlight >}}

{{< highlight css>}}
/* css code */
.box {
  height: 100px;
  width: 200px;
  border: 1px solid black;
  color: white;
  cursor: pointer;
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
  margin-top: 10px; /* add some spacing above box2 ... maybe? */
 }
{{< / highlight >}}

<div style="width: 200px; margin: 0 auto;">
<div class="box1" style="height: 100px;
   width: 200px;
   background-color: orange;
   border: 1px solid black;
   color: white;
   cursor: pointer;
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
   cursor: pointer;
   display:flex;
   justify-content:center;
   align-items: center;
   margin-top: 10px;">
   box2
 </div>
</div>

We can now see some spacing between box1 and box2 but there is a subtle effect that is taking place.

Since both box1 and box2 are right next to each other the top and bottom margin  will collapse to only the element with the largest margin. Without this effect we should have had a total margin between boxes of 30px because we added some botton margin of 20px to box1 and some top margin of 10px to box2. 

Margin collapse is what's happening with our example above and we will only get 20px of margin from box1 ignoring the top margin of box2. 

Another property of margin is that it is always transparent and it will not take the background color of the element it was added to.

## Padding

Using our example above lets switch margin to padding.

{{< highlight html >}}
<!-- html code -->
<div class="box box1">box1</div>
<div class="box box2">box2</div> 
{{< / highlight >}}

{{< highlight css>}}
/* css code */
.box {
  height: 100px;
  width: 200px;
  border: 1px solid black;
  color: white;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}

.box1 {
  background-color: orange;
  padding-bottom: 20px; /* add some spacing below box1 */
} 

.box2 {
  background-color: green;
  padding-top: 10px; /* add some spacing above box2 … maybe? */
}
{{< / highlight >}}

<div style="display: flex; align-items:center;
flex-direction:column;">
  <div class="box1" style="height: 100px;
width: 200px;
background-color: orange;
border: 1px solid black;
color: white;
cursor: pointer;
display:flex;
justify-content:center;
align-items: center;
padding-bottom: 20px;">
box1
</div>
<div class="box2" style="height: 100px;
width: 200px;
background-color: green;
border: 1px solid black;
color: white;
cursor: pointer;
display:flex;
justify-content:center;
align-items: center;
padding-top: 10px;">
box2
</div>
</div>

Right away we can see the difference the effect padding has on our elements.

Padding is added within the border of our elements and this lets it take on that elements background color. As a result we cannot really see any seperation between box1 and box2.

Unlike margin, padding does aggregate between elements that are right next to each other. In our example box1 with bottom padding of 20px and box2 with top padding of 10px show a total of 30px of extra space between them.

One last consideration to using padding over margin is the available click area of an element. Hovering over our elements extra space given by padding will still allow us to interact with that element while with margin spacing we no longer have that ability.



 
