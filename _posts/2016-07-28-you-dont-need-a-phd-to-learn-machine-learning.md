---
layout:     post
title:      You Don't Need a Ph.D. to Learn Machine Learning
date:       2016-07-28 12:00:00
summary:    Data scientists do not usually create their own algorithms: what a relief.
categories: data-science
comments:   true
---

Surprise! Data science doesn't have to be impossible.  

What I learned:  data scientists regularly help each other by creating -- and re-using -- publicly available algorithms. This clearly makes their lives easier, as they can lean on tried-and-true solutions without having to reinvent the wheel each time they manipulate datasets.  

Wow. And here I thought, every data scientist comes up with his or her own algorithm every day.  This is not the case, apparently.

I learned this after attending two recent machine learning Meetups. At the [Machine Learning Hackathon](http://www.meetup.com/Miami-node-js-Meetup/events/228588822/) I attended back in February (yes, I should have blogged about it back then, because it was so awesome), facilitator [Luc Castera](http://luccastera.com/) actually gave us a list of algorithms to choose from. I was stunned, thinking, 'Why would a data scientist, after working so hard, make these publicly available?'  I actually thought that Luc was just trying to be nice to us, since so many of us in the group were newbies to machine learning.

The assignment that night: [predict the survivors of the Titanic](https://www.kaggle.com/c/titanic). WTH? I thought, then Luc explained that it was part of a public competition on competitive data science portal [Kaggle](http://www.kaggle.com), which was brilliant, even though my team ended up losing.

My team selected a [NodeJS implementation of Decision Tree](https://github.com/serendipious/nodejs-decision-tree-id3), which uses the [ID3 algorithm](https://en.wikipedia.org/wiki/ID3_algorithm).

![The Kaggle competition.](http://i63.tinypic.com/5al6hk.jpg)

A similar situation occurred this week when attending the Fort Lauderdale Machine Learning [Meetup](http://www.meetup.com/Fort-Lauderdale-Machine-Learning-Meetup/events/232388112/), 'Zero to Hero in One Session: A Hands-On Approach to R Programming,' led by data scientist and R evangelist [Pierre Lafortune](http://stackoverflow.com/users/4564247/pierre-lafortune). (Yes, he is in the top 0.41% on Stack Overflow this year.)

The hands-on learning included the group having to download and be introduced to [RStudio](https://www.rstudio.com/home/), which was a relief, since the Intro to R course on [DataCamp](https://www.datacamp.com/home) I went through never actually explained *where* or *how* an R programmer programs in R.

Pierre provided all of the datasets and instructions beforehand, but walked us through step-by-step how to clean, organize, merge, visualize, and most importantly, use algorithms to make predictions for what was missing.

And you guessed it:  he provided the algorithms for us.

One was [Random Forest](https://cran.r-project.org/web/packages/randomForest/index.html), for classification/clustering and regression. This was easily added via the Install function in RStudio.

I suppose I should not be surprised that data scientists use and re-use already-published algorithms:  the open source community boasts Ruby gems and Javascript libraries numbering in the thousands.  

As a result of the relative friendliness and approachability of the facilitators of these two machine learning events, I have taken a much stronger interest in learning data science.  I'm not yet ready to attend a bootcamp, such as those offered by [Galvanize](http://www.galvanize.com/courses/data-science/#.V5uYSI5_xak) or [Metis](http://www.thisismetis.com/data-science-bootcamps), but I definitely plan to strengthen my R and Python skills.

Sadly, the Intro to Python course I took on Treehouse has been deprecated and I will now need to re-learn Python. Does anyone have any suggestions for a good Python course, with emphasis on its usage in data science?

I think another reason I am gravitating towards data science is that the discipline is actually doing something useful: answering questions, solving problems, visualizing numbers, making decisions, and simplifying what is seemingly complex.  And isn't that what software development is supposed to do for the world?
