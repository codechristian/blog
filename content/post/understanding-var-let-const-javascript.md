---
title: "Understanding Var, Let, And Const In JavaScript"
date: 2017-10-24T08:14:51-07:00
draft: false
---

## var 
Declaring a variable with the <code class="code-key">var</code> keyword results in it having function scope. 

This means that we are able to use a variable with the <code class="code-key">var</code> keyword outside of the block it was declared in.

{{< highlight javascript >}}
//start of printMessage function scope
function printMessage(message, times) {
  
 //start of for loop block scope
 for (var i = 0; i < times; i++) { 
   
 console.log(message);
   
 }//end of for loop block scope.
  
 //i variable used outside of for loop block it was declared in
 console.log('Value of i is ' + i); 
  
}//end of printMessage function scope

printMessage('hello', 3);

//using i outside of its function scope results in an error
console.log('Value of i is ' + i); 
{{< / highlight >}}

In the above example we are able to declare a <code class="code-key">var</code> variable <code class="code-key">i</code> inside a for loop block within the function printMessage. Since we declared <code class="code-key">i</code> with the keyword <code class="code-key">var</code> we are able to use it outside of the for loop block.

We will also get an error if we try and use our variable <code class="code-key">i</code> outside of its function scope.

## let

The <code class="code-key">let</code> keyword will give our declared variables block scope. We will no longer be able to use a <code class="code-key">let</code> variable outside of its block scope without getting an error.

{{< highlight javascript >}}
//start of printMessage function scope
function printMessage(message, times) {
  
 //start of for loop block scope
 for (let i = 0; i < times; i++) { 
   
   console.log(message);
   
 }//end of for loop block scope.
  
 //using i outside of its block scope results in an error
 console.log('Value of i is ' + i); 
  
}//end of printMessage function scope

printMessage('hello', 3);
{{< / highlight >}}

## const

Like <code class="code-key">let</code>, declaring a variable with the <code class="code-key">const</code> keyword will restrict that variable with block scope. 

{{< highlight javascript>}}
//start of printMessage function scope
function printMessage(){
  
  let x = 10;
  
  //start of if statement block scope
  if (x > 0) {
    
    const y = 11;
    
    //const variable used within declared block scope
    console.log(y);
    
  }//end of if statement block scope
  
  //error! const variable used outside block scope
  console.log(y);
  
}//end of printMessage function scope

printMessage();
{{< / highlight >}}

The difference is that a variable declared with the <code class="code-key">const</code> keyword cannot be reassigned. 

{{< highlight javascript>}}
//declare let variable
let x = 10;

//use x variable with let keyword
console.log(x);

//reassigning value of x is ok
x = 9;

//use reassigned x variable with let keyword
console.log(x);

//declared const variable
const y = 11;

//error! once we try and reassign the value of const variable y
y = 12;
{{< / highlight >}}

If you require that declared variables be able to change (e.g. <code class="code-key">for</code> loops) then <code class="code-key">let</code> is the ideal keyword of choice. In any other case using <code class="code-key">const</code> whenever possible is preffered.