---
layout: post
title: "Goodbye Octopress, Hello Jekyll"
date: 2014-01-07 08:30
comments: true
categories: jekyll
keywords: octopress,jekyll,blogging,wordpress
descripton: I switched from Octopress to Jekyll and never looked back.
---

It wasn't long ago that I got my octopress blog up and running nicely. For those of you who don't know, [Octopress](www.octopress.org) is a framework for [Jekyll](www.jekyllrb.com) which is a static website generator. Since then, I've fallen in love with static website publishing. The fact that I can write my posts in markdown and push them up to github to update my blog has been a wonderful thing. I love having direct access to all of my posts as well. I know I can use them in whatever way I wish and that I'm not tied to a 3rd party service. Needless to say, I'm a fan of static site publishing.

Recently I decided I needed to put up somewhat of a landing page for my personal use. As we get back to the states next year and I start to look for a job, I needed to have something showing my current projects and what I've worked on before. With a project idea under my belt, I decided to try to learn something new along the way. I've used [Twitter Bootstrap](getbootstrap.com) before and wanted to branch out some. I also thought Bootstrap might be a bit heavy for my needs. Some of the ones I came across included [Susy](susy.oddbird.net),[Zurb's Foundation](foundation.zurb.com), and [Bourbon Neat](neat.bourbon.io). 

After looking through the options, I decided to go with _Bourbon Neat_. I was initially attracted to it because its lightweight and the way it handles the grid. Unlike bootstrap, you handle all the grid settings in the css files and use your normal divs in your html markup. Its also maintained by the wonderful folks over at [thoughtbot](thoughbot.com) so you know its a quality framework.

After looking at everything, I was excited. I was ready to begin.

I ran into a problem though. My octopress blog didn't match my personal site. Like, *at all*. Me being the somewhat OCD person I am, could not have this at all. It has to be right. So I set out to see what I could do. I tried tinkering with the octopress stuff for a good few hours until I decided I was just fed up with it. I kept trying to integrate my design into the existing octopress template (which I'm sure was the wrong way to do it) and it wasn't working. 

It felt bloated. Lately, I've really come to apreciate things that are more on the simplistic side of life. If I don't use it, I don't need it type of mentality. I know that Octopress is a wrapper around the real magic of Jekyll. I thought to myself, I should just try vanilla Jekyll. So I did. And **I love it.**

Its really easy to get up and running. As per the instructions on [http://jekyllrb.com/](jekyllrb.com)

{% highlight ruby %}
~ $ gem install jekyll
~ $ jekyll new my-awesome-site
~ $ cd my-awesome-site
~/my-awesome-site $ jekyll serve
{% endhighlight %}


Then go to localhost:4000 in your browser to see your new website. Awesome. After that, I began tinkering even more and learning how to use scss. I might do a post later on on that, as I also fell in love with it as well. This is the perfect setup for me. Being able to deploy on Github is also a huge plus. It integrates with my workflow flawlessly, and is very programmer friendly.