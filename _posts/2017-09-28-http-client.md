---
layout: post
title: "How do I make HTTP requests to the GitHub API?"
date: 2017-09-28 10:52:54
image: '/assets/img/'
description:
tags: howto project
categories:
---

In the GitHub Analytics project, we want to make requests to the GitHub API (v3) to fetch data. It is a REST API, so these are HTTP requests. What is the best way to make them in our code? As always, there are different approaches and we will compare three in this post.

## Approach 1: use a wrapper

If you don't want to bother with all the details of the REST API, you can decide to use a wrapper such as [this one](https://www.npmjs.com/package/github). You will get a Javascript API and a set of classes that map to the GitHub resources (repositories, issues, etc.). The wrapper will also make it a bit easier for you to do some tasks, such as using authentication or dealing with pagination. On the downside, you will have to learn the Javascript API so you might not save a lot of time.

Our opinion: given the (low) complexity of this project, it is probably not that useful to use a wrapper.

## Approach 2: make the HTTP calls with the core Node.js API

Node.js provides APIs to make HTTP calls. Have a look at the [HTTP module](https://nodejs.org/api/http.html) documentation. It is pretty straightforward to use. It will work. However, you will most likely feel that the code that you write is a bit verbose and that you have to explicitly deal with a lot of details.

Our opinion: most people prefer a higher-level API to issue HTTP requests, and so do we.

## Approach 3: use an HTTP client library

There are several npm modules that provide nice abstractions on top of the Node.js HTTP module. One example is [superagent](https://www.npmjs.com/package/superagent), another example is [axios](https://www.npmjs.com/package/axios). In the course, we have not seen [promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) yet and have only worked with callbacks. This is one reason why we have used `superagent` in the webcast.

Our opinion: use `superagent`: it is simple, elegant and works very well. Note that you can even extend its functionality with plugins, for example to use throttling, promises and other features.

