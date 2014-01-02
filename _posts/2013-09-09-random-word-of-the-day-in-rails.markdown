---
layout: post
title: "Random word of the day in rails"
date: 2013-09-09 14:26
comments: true
categories: [ruby,rails,tutorial]
keywords: ruby,rails,word,day,random,
descripton: How to implement a random word of the day in rails.
---
The best part about deploying a site that is functioning properly is getting to add fun new features into it.

Currently I'm working on implementing a word of the day into a language timesheet tracker site I have been working on. My initial thought was to use a textfile and pair up the words with a **Word** - *Definition* type structure. However this proved to be difficult because I'm dealing with a different language. The Khmer Language kept giving me lots of issues.


So the way I wanted it setup was to show the Khmer *word*, the english *translation*, and only show **one** each day.

I decided to try my hand at writing my own. I decided to go the route of just generating a new table in the database of words. That way whoever is an admin can get in and add any words they want to at their hearts desire.

Here is the code I used.


{% highlight ruby %}
rails g scaffold Word khmer english rndm
{% endhighlight %}

Then thanks to a helpful stack overflow post, i was able to pop this code in to my Word Model.

````
class Word < ActiveRecord::Base
  def self.random
    rndm = find_by_rndm Date.today
    unless rndm
      update_all :rndm => nil
      rndm = self.order('rand()').first
      rndm.update_attribute :rndm, Date.today
    end
    rndm
  end
````

**Boom shackalacka.** It works. Now all I had to do was call <code>Word.random</code> in my specific controller I wanted which for me was my Home Controller and set it to an instance variable like so.

````
@khmer = Word.random.khmer
@english = Word.random.english
````

We'll see if it works tomorrow when the date changes. :) Easy as that!
