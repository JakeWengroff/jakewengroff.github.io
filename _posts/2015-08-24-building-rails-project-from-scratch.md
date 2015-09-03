---
layout:     post
title:      Building a Rails Project from Scratch
date:       2015-08-24 15:09:41
summary:    A constant, pesky LoadError keeps preventing me from generating Rails projects. What to do?
categories: ruby rails
comments:   true
---

I had some *serious* issues with my installed Ruby and Rails versions back in April of this year. My PATH was messed up, and I also think there was a problem with some gemsets.

I upgraded to Yosemite and also upgraded to Xcode version 6.3, but problems still persisted.

Though I could handle things via workarounds, one of the biggest headaches which I still must endure is that **I cannot create a Rails project from scratch**.

A simple command to create a Rails project titled JakeMarks,

```
rails new JakeMarks -T
```

yields:

{% highlight ruby %}
script/rails:5:in `require': cannot load such file -- /Users/JakeWengroff/config/boot (LoadError)
	from script/rails:5:in `<main>'
{% endhighlight %}

Argh.

A quick look in my ```JakeWengroff``` folder shows me that there is no ```config``` folder *at all* so where could this offending error be?

I Googled. I StackOverflowed. Nothing worked.

Finally, I decided:  if I need to generate a new Rails project, I will need to create it from scratch.  Tedious, but I had no choice, as the deadline for the next deliverable ('Checkpoint') for my online bootcamp course was looming quickly on the horizon.

Here's basically what I did.

I visited the good ole' [Ruby on Rails Guides](http://guides.rubyonrails.org/getting_started.html#creating-the-blog-application) to tell me what folders to create. I wasn't creating a Blog application, but I figured that this would be a good start.

Here is a screenshot of the folders I created.  (I decided to omit Minitest, or the test suite, because I planned on using [RSpec](http://rspec.info/). RSpec has been a preference for my last two Rails courses.)

![Basic Rails app folders](http://i62.tinypic.com/2jdosqa.jpg)

(The screen grab missed the last folder, which is ```vendor/```, for all third-party code.)

The ```app``` folder was easy.  I didn't fuss with creating the ```assets```, ```controllers```, ```models```, or ```views``` sub-folders, since I could generate these from the command line.

The ```bin``` folder added a bit more labor.  I recalled that this folder contains important files that essentially make the app run.  I pulled up a recently completed Rails app and copied the ```bundle```, ```rails```, ```rake```, ```setup```, and ```spring``` files one by one.  More Argh.  

The tedium was settling in.

The ```config``` folder required even more copy and pasting.  This includes sub-folders ```environments```, ```initializers```, and ```locales``` (these three each having their own additional files), in addition to ```application.rb```, ```boot.rb```, ```database.yml```, ```environment.rb```, ```routes.rb```, and ```secrets.yml```.

I won't list every single file I copied and pasted. But I just kept going, aiming to have everything done in less than 30 minutes.

To be on the safe side, even if there were empty files, I still created that folder and all associated empty files.  

For example, both the ```log``` and ```tmp``` folders, along with each of their files, were really just empty.

![log folder](http://i61.tinypic.com/k1x7rq.jpg)

But it's obviously important to have the log files, as they will be populated during the development and testing of the app.

![tmp folder](http://i60.tinypic.com/jszyxl.jpg)

Rounding out the copying and pasting were the ```.gitignore```, ```config.ru```, ```Gemfile```, ```Gemfile.lock```, ```Rakefile```, and ```README.md``` files.

My system did not prove to be perfect.  Errors abounded, as some of my copy and pasting included specific code for other apps, which needed to be adjusted for the new app.

But having to reluctantly go through this exercise helped me learn more about the underlying structure of a Rails app.  Still more learning for me to do, but sometimes in the tedium lies the learning.  
