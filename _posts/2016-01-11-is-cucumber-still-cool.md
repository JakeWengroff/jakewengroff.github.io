---
layout:     post
title:      Is Cucumber Still Cool?
date:       2016-01-11 09:09:41
summary:    It's all about Behavioral Driven Development, after all.
categories: ruby rails
comments:   true
---

Testing, testing, testing: my coding mentor was successful in driving into my brain the importance of a codebase with proper, passing tests.

My Bloc Web development apprenticeship introduced me to [Rspec](http://rspec.info/), and I learned how to write about a dozen or so Rspec tests for a handful of Rails apps.

I quickly learned the joy of running tests and seeing the string of asterisks followed by ```0 failures```.

A recent interview for an opportunity for consulting work included the invariable question, 'What can you do for me?'

My immediate response:  'Let me write tests.'

'Do you know Cucumber?' he asked.

'I've heard of it, but I've never used it,' I replied.

The potential client then asked me to add [Cucumber](https://cucumber.io/) tests to an existing Rails app -- this would be my coding challenge.

![The Cucumber homepage.](http://i63.tinypic.com/dpitra.jpg)

<h3>Looks Can Be Deceiving</h3>
Cucumber was supposedly developed for non-techies. The idea was that non-developers could literally write their list of user stories right into the codebase.  

But then, of course, the developer would have to go ahead and write the tests -- presumably adding an extra layer of administrative work because any good developer would have written tests anyway.

(Google searches on Cucumber led me to several blogs and YouTube videos where developers expressed their downright opposition to Cucumber, but I digress.)

Anyhoo, it starts out easy enough.  I decided to add Cucumber tests to one of my simpler bootcamp apps, [Jake It Off!](https://github.com/JakeWengroff/jake-it-off), a self-deleting To-Do List app.  

To start, all I had to do was add this to the Gemfile:

{% highlight ruby %}
group :development, :test do
  gem 'cucumber-rails', :require => false
end
{% endhighlight %}

then in the terminal run
{% highlight ruby %}
rails generate cucumber:install
{% endhighlight %}

followed by
{% highlight ruby %}
rake cucumber
{% endhighlight %}

then
{% highlight ruby %}
cucumber features
{% endhighlight %}

which of course produced nothing to speak of
{% highlight ruby %}
Using the default profile...
0 scenarios
0 steps
0m0.000s
{% endhighlight %}

I proceeded to add the ```step_definitions``` folder to the ```features``` folder, and created two new files: ```item_steps.rb``` and ```create_items.feature```.

I added this English language to the ```create_items.feature``` file:
{% highlight ruby %}
Feature: Create items
  In order to make a To-Do List
  As a user
  I want to add items

  Scenario: Items List
    Given I am logged in as a user
    When I fill in the form with a new Item
    Then I see a new Item
{% endhighlight %}

Now, when running ```cucumber features```, I get the output

{% highlight ruby %}
Using the default profile...
Feature: Create items
  In order to make a To-Do List
  As a user
  I want to add items

  Scenario: Items List             # features/create_items.feature:6
    Given I am logged in as a user # features/create_items.feature:7
      Undefined step: "I am logged in as a user" (Cucumber::Undefined)
      features/create_items.feature:7:in `Given I am logged in as a user'
    When I fill in the form with a new Item     # features/create_items.feature:8
      Undefined step: "I fill in the form with a new Item" (Cucumber::Undefined)
      features/create_items.feature:8:in `When I fill in the form with a new Item'
    Then I see a new Item         # features/create_items.feature:9
      Undefined step: "I see a new Item" (Cucumber::Undefined)
      features/create_items.feature:9:in `Then I see a new Item'

1 scenario (1 undefined)
3 steps (3 undefined)
0m0.042s

You can implement step definitions for undefined steps with these snippets:

Given(/^I am logged in as a user$/) do
  pending # express the regexp above with the code you wish you had
end

When(/^I fill in the form with a new Item$/) do
  pending # express the regexp above with the code you wish you had
end

Then(/^I see a new Item$/) do
  pending # express the regexp above with the code you wish you had
end
{% endhighlight %}

Wow, so no errors -- just scenarios and steps that are undefined.  And how nice that they gave me code snippets. But what to do next?


<h3>Acting Alone</h3>
Cucumber tests are not written alone. In fact, Cucumber isn't a standalone testing package; to my understanding, it's simply a wrapper and requires Rspec, Capybara, Selenium, and other test applications in order for it be functional.

Thank God, because I was totally lost. What did I do next?  I relied on good ole' Rspec.

It took a few tries -- ok, a couple of hours -- but my ```item_steps.rb``` file eventually became:

{% highlight ruby %}
Given(/^I am logged in as a user$/) do
  visit "/"
end

When(/^I fill in the form with a new Item$/) do
  visit 'users/items' do
    fill_in 'Add a To-Do', :with => item
  end
end

Then(/^I see a new Item$/) do
  visit 'user' do
    expect(page).to have_content 'Success'
  end
end
{% endhighlight %}

<h3>Sweet Victory</h3>
Of course, victory comes in many forms, most notably when there are no failures:

{% highlight ruby %}
Using the default profile...
Feature: Create items
  In order to make a To-Do List
  As a user
  I want to add items

  Scenario: Items List                      # features/create_items.feature:6
    Given I am logged in as a user          # features/step_definitions/item_steps.rb:1
    When I fill in the form with a new Item # features/step_definitions/item_steps.rb:5
    Then I see a new Item                   # features/step_definitions/item_steps.rb:11

1 scenarios (1 passed)
3 steps (3 passed)
0m0.968s
{% endhighlight %}

<h3>The Logic Was All Wrong</h3>
But I was missing the point of writing Cucumber tests.

The idea of Test Driven Development or Behavior Driven Development is to write the tests *first* and *then* write the code.  

But I was doing it in reverse.

What I was doing was akin to offering to write the outline of a novel after the novel was already written.

But that's OK.  I can always use good practice in writing tests.

What are your thoughts on Cucumber?  Leave a comment below or [message me]({{ site.baseurl }}/contact/) -- I'm curious to hear your thoughts.
