---
layout: blog
comments: true
title:  "Reflections on static site generators"
date:   2016-11-14 20:43:00
categories: jekyll
---

-What do you think of pre-compiling your CSS?

Pre-compiling code is a common practice in web development, this could for example be to compile more recent
versions of JavaScript into an older version to run on older browsers. There are a growing number of languages like
ClojureScript, Elm and Haskell which can be compiled to JavaScript in order to run in the browser.
So pre-compiling CSS code is not such a huge step to add into a development workflow.
From a programmers perspective, CSS is quite a messy language so I am very happy if I can avoid it!

-Compare to regular CSS

CSS pre-processors extends CSS with additional capabilities that can be very useful to make cleaner code that is less
repetitive and better organized. The use of variables for example can be used to define a commonly used color, which
means you only need to change it in one place if you decide it is ugly!
The ability to write functions could for example be used to create a variation of a color, except darker or lighter.
If/Else statements can be used to use different styles based on some conditions. Loops can be used to iterate through
arrays or create series of styles.
Nesting can help make the code more organized into clear levels, for people who are used to programming languages this
feature makes a lot of sense.
Extend may be used as a kind of inheritence to allow a class to inherit properties from other classes.

-Which techniques did you use?

I made use of variables for commonly defined values so they only need to be written once.

Pros and cons?

-What do you think of static site generators?

They can be useful for quickly making content-focused sites with static content... like blogs! It was a little bit tricky
to get started at first since I had not used something similar before. But I have done some PHP coding where I would make
use of a lot of partial sites which I would include into bigger pages. However for these PHP websites that I made I would
make use of an SQL database to store posts for example. Overall I would say that was more complicated then using a static
site generator since using a database you must write some code to perform CRUD operations (create, read, update, delete).
The database can also be an attack vector for potential hackers so it requires additional security concerns like escaping
strings that could carry SQL injections. So in that sense static site generators are simple.

-What type of projects are they suitable for?

If only static content needs to be served and for example no user accounts are required (which would need a database
backing the site). Anything that would require a database would not be a good fit for using a static site generator.

-What is robots.txt and how have you configure it for your site?

It is a file which can be read by web crawlers as they explore and index the web, the content you put in robots.txt
can instruct these web crawlers on how to behave on your site... there is no guarantee that they will however so it
is mostly a courtesy thing which might not be respected! Especially if your site is crawled to be potentially attacked
in some way.

-What is humans.txt and how have you configure it for your site?

This is a file to be read by the mythical human beast who (allegedly) also crawl the web along with their robot friends.
The purpose of this file is to share who has made the website and perhaps other kinds of information, like what technology,
techniques, tools etc were used in the process.

-How did you implements comments to blog posts

I used Disqus by setting comments to true in the yaml front matter. In my blog layout file (blog.html), I used the
liquid templating language to add a conditional if statement that will execute code if comments are set to true.
Inside of this if statement I put the universal embed code provided by Disqus.

-What is Open Graph and how do you make use of it?

Open Graph is a protocol that "enables any web page to become a rich object in a social graph."
(<a href="http://ogp.me/" target="_blank">http://ogp.me/</a>). It was created by Facebook to connect actions and objects
to facebook, and ultimately to people. Using the open graph websites can have user activity on their website show up
on the feeds of facebook users, so for example people on facebook can see what their friends are doing on the rest of
the web.
I used the instructions on the open graph website to add basic metadata tags (title, type, image, url) in my head
includes file. I also used some code from this blog:
<a href="http://davidensinger.com/2013/04/adding-open-graph-tags-to-jekyll/" target="_blank">davidensinger</a>
to add category and tags metadata.
