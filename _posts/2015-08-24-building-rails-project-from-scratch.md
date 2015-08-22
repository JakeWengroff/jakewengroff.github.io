---
layout:     post
title:      Building a Rails Project from Scratch
date:       2015-08-24 15:09:41
summary:    A constant, pesky LoadError prevents me from generating Rails projects. What to do?
categories: ruby rails
comments:   true
---

I had some *serious* issues with my installed Ruby and Rails versions back in April of this year. My PATH was messed up, and I also think there was a problem with some gemsets.

I upgraded to Yosemite and also upgraded to Xcode version 6.3, but problems still persisted.

Though I could handle things via workarounds, one of the biggest headaches which I still must endure is that I cannot create a Rails project from scratch.

A simple command to create a Rails project titled JakeMarks, ```rails new JakeMarks -T```

yields:

{% highlight ruby %}
script/rails:5:in `require': cannot load such file -- /Users/JakeWengroff/config/boot (LoadError)
	from script/rails:5:in `<main>'
{% endhighlight %}

Argh.

A quick look in my ```JakeWengroff``` folder shows me that there is no ```config``` folder *at all* so where could this offending error be?

I Googled. I StackOverflowed. Nothing worked.

Finally, I decided:  if I need to generate a new Rails project, I will need to create it from scratch.  Tedious, but I had no choice, as the deadline for the next deliverable ('Checkpoint') for my online bootcamp course was coming up quickly.

Here's basically what I did.

First off, I created a ton of new folders using the good ole' [Ruby on Rails Guides](http://guides.rubyonrails.org/getting_started.html#creating-the-blog-application) to tell me what folders to create. I wasn't creating a Blog application, but this would be a good start.

Here is a screenshot of the folders I created.  (I decided to omit Minitest, or the test suite, because I planned on using [RSpec](http://rspec.info/). RSpec has been a preference for my last two Rails courses.)

![Basic Rails app folders](http://i62.tinypic.com/2jdosqa.jpg)

The screen grab missed the last folder, which is ```vendor/```, for all third-party code.  
