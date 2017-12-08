---
title: "Installing Node.js With NVM On Ubuntu Using Terminal"
date: 2017-10-22T22:38:55-07:00
draft: false
---

## NVM

Node Version Manager lets us install and switch between several versions of node.js.

First we should update our packages:

{{< highlight bash >}}
$ sudo apt-get update
{{< / highlight >}}

Next we will install the latest version of NVM from [this github repo](https://github.com/creationix/nvm). As of this post the most recent NVM is v0.33.5. We can use the following command to begin installation.

{{< highlight bash >}}
$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.5/install.sh | bash
{{< / highlight >}}

Now follow the terminal instruction after the NVM install is complete:

{{< highlight bash >}}
$ Close and reopen your terminal to start using nvm
{{< / highlight >}}

Lets check if we now have NVM installed:

{{< highlight bash >}}
$ nvm --version
{{< / highlight >}}

This should give you the version of NVM that you installed:

{{< highlight bash >}}
$ 0.33.5
{{< / highlight >}}

## Node.js

Now we can install the latest stable version of node.js:

{{< highlight bash >}}
$ nvm install stable
{{< / highlight >}}

We can check our current version of node.js:

{{< highlight bash >}}
$ node --version
{{< / highlight >}}

The current stable node.js version as of this post is:

{{< highlight bash >}}
$ v8.7.0
{{< / highlight >}}