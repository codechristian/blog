---
title: "Understanding Var, Let, And Const In JavaScript"
date: 2017-10-24T08:14:51-07:00
draft: false
---

## var 
Declaring a variable with the <code class="code-key">var</code> keyword results in it having function scope. 

This means that we are able to use a variable with the <code class="code-key">var</code> keyword outside of the block it was declared in.

<a class="jsbin-embed" href="http://jsbin.com/pibinegasi/embed?js,console">JS Bin on jsbin.com</a><script src="https://static.jsbin.com/js/embed.min.js?4.1.0"></script>

In the above example we are able to declare a <code class="code-key">var</code> variable <code class="code-key">i</code> inside a for loop block within the function printMessage. Since we declared <code class="code-key">i</code> with the keyword <code class="code-key">var</code> we are able to use it outside of the for loop block.

We will also get an error if we try and use our variable <code class="code-key">i</code> outside of its function scope.

## let

The <code class="code-key">let</code> keyword will give our declared variables block scope. We will no longer be able to use a <code class="code-key">let</code> variable outside of its block scope without getting an error.

<a class="jsbin-embed" href="http://jsbin.com/xufuweniri/embed?js,console">JS Bin on jsbin.com</a><script src="https://static.jsbin.com/js/embed.min.js?4.1.0"></script>

## const

Like <code class="code-key">let</code>, declaring a variable with the <code class="code-key">const</code> keyword will restrict that variable with block scope. 

<a class="jsbin-embed" href="http://jsbin.com/ceqedejise/embed?js,console">JS Bin on jsbin.com</a><script src="https://static.jsbin.com/js/embed.min.js?4.1.0"></script>

The difference is that a variable declared with the <code class="code-key">const</code> keyword cannot be reassigned. 

<a class="jsbin-embed" href="http://jsbin.com/vurerasoja/embed?js,console">JS Bin on jsbin.com</a><script src="https://static.jsbin.com/js/embed.min.js?4.1.0"></script>

If you require that declared variables be able to change (e.g. <code class="code-key">for</code> loops) then <code class="code-key">let</code> is the ideal keyword of choice. In any other case using <code class="code-key">const</code> whenever possible is preffered.