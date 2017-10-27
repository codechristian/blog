---
title: "Installing Node.js With NVM On Ubuntu Using Terminal"
date: 2017-10-22T22:38:55-07:00
draft: false
---

## NVM

Node Version Manager lets us install and switch between several versions of node.js.

First we should update our packages:
<pre class="code">
<code>
  $ sudo apt-get update
<code>
</pre>

Next we will install the latest version of NVM from [this github repo](https://github.com/creationix/nvm). As of this post the most recent NVM is v0.33.5. We can use the following command to begin installation.

<pre class="code">
<code>
  $ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.5/install.sh | bash
<code>
</pre>

Now follow the terminal instruction after the NVM install is complete:
<pre class="code">
<code>
  $ Close and reopen your terminal to start using nvm
<code>
</pre>

Lets check if we now have NVM installed:
<pre class="code">
<code>
  $ nvm `--`version
<code>
</pre>

This should give you the version of NVM that you installed:
<pre class="code">
<code>
  $ 0.33.5
<code>
</pre>

## Node.js

Now we can install the latest stable version of node.js:
<pre class="code">
<code>
  $ nvm install stable
<code>
</pre>

We can check our current version of node.js:
<pre class="code">
<code>
  $ node `--`version
<code>
</pre>

The current stable node.js version as of this post is:
<pre class="code">
<code>
  $ v8.7.0
<code>
</pre>


