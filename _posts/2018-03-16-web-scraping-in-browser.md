---
published: true
title: Scraping YouTube Trends in Browser
tags: >-
  web scraping parsing parserr youtube trends javascript DOM allorigins bypass
  cors
---
Anyone faces the need of web scraping sooner or later. There might be no API at all, or it may be private and so on. Usually, developers using scripting languages like PHP and tools like Symfony DomCrawler(yeah, I am very PHP biased) for scraping web pages and parsing DOM. But let’s say that we do not have an environment for running scripting languages, we do not have a server, or we are just too lazy to run node.js and don’t want to use anything but javascript. For this case, we can go serverless and do all stuff on the client side!

The first problem that we will face is CORS. Truly, we can’t just send a request to any web page we want. Or can we? [AllOrigins](http://multiverso.me/AllOrigins/) to the rescue. This service simply works as a proxy and can deliver us any web page we want. So let’s create a function for bypassing CORS.

{% gist 36408a65d09ae812902264c7db718c5e %}

As an example, we let's get a list of current YouTube trends. In short research, i’ve noticed that each element of a list has a **yt-lockup-title** class, and its child element contains a link to the video. Link itself has the **yt-uix-tile-link** class. So we can select elements of interest by this css selector: **.yt-lockup-title > .yt-uix-tile-link**.

Let's create a function for getting a list of trends:

{% gist 2f07e80cf1d366b6371448d8c07af68a %}

We've created a div element and loaded the content of YouTube page into its innerHTML. After this, we can simply use a querySelector method and get a list of necessary nodes which we will transform into a list of trend objects(a list of simple object containing 2 properties: video URL and title.

The result can be used for rendering something or doing any stuff you’d need. In the example below I will just create a list of links.

[Complete example on jsfiddle](https://jsfiddle.net/bxo0thou/1/)

Have fun scraping!
