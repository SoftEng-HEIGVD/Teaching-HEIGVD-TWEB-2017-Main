---
layout: post
title: "What is a linter?"
date: 2017-09-19 13:45:30
image: '/assets/img/'
description:
tags:
categories:
---

Developers need rapid and frequent feedback. It makes them better. It makes their code better.

Linters are one way to automatically provide  feedback to developers. The feedback is about code quality, code smells and coding guidelines.

A linter is a tool that performs a static analysis of your code and applies a set of rules to detect potential problems.

For instance, it is easy for a linter to detect that a variable has been initialized but has never been reused. Is that a problem? Well, maybe it suggests that the developer has made a typo:

{% highlight javascript %}
const perfection = 'is nice';
console.log(ferpection); // undefined
{% endhighlight %}

Another important issue, especially when developing in teams, is to agree on conventions and to follow them. Should we use tabs or spaces? How should we name functions? Having clear rules helps with consistency. This is very important, especially if you think about the evolution and the maintenance of the codebase. Ask yourself this question: 

> If another developer needs to modify this file, how much time will he need to read and understand it?

A uniform codebase helps reduce this time. A uniform codebase helps save money.

## Linters for Web development

Static code analysis is particularly useful for web developers. A common complaint about Javascript is the fact that it is too easy to write messy and fragile code. There is not even a compiler to capture some of the errors introduced by developers. Guess what: a linter is precisely a tool that fills addresses this issue. In fact, it does more and is able to detect all sorts of bad practices.

## Put it in practice with ESLint

There are different Javascript linters in the community. JSHint and JSLint are two examples. Sonarlint is another one. The one that we propose to use is [ESLint](https://eslint.org/). It is very popular and has a nice pluggable architecture, which makes it extensible and configurable. ESLint can also be integrated with Visual Studio Code, which means that developers can get feedback directly in the IDE (and not only during the build process).

The rules are documented [here](https://eslint.org/docs/rules/).

You can install ESLint with `npm`. In our setup, we install it locally to the project (not globally, with the `-g` flag). One thing to be aware, when using ESLint with Visual Studio Code, is that you need to restart the IDE whenever you change the linter configuration. [This might change in the future](https://github.com/Microsoft/vscode-eslint/issues/164).

{% highlight bash %}
# install eslint locally to the project
npm install --save-dev eslint

# initialize the config... follow the instructions
./node_modules/estlint/bin/eslint.js --init

# run the linter on your source file and see the result in the console
./node_modules/eslint/bin/eslint.js mycode.js
{% endhighlight %}

For french speakers, we have recorded a webcast that shows how to install ESLint, how to configure it with the [Airbnb Style Guide](https://github.com/airbnb/javascript) and how to use it in Visual Studio Code. 

<iframe width="640" height="360" src="https://www.youtube.com/embed/53IM2NYMH4Q" frameborder="0" allowfullscreen></iframe>
