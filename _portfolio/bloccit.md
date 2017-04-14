---
layout: post
title: Bloccit
thumbnail-path: "img/reddit.svg"
short-description: Bloccit is an app that I built that's based on the fan fave Reddit, "the front page of the internet".
---
Welcome to Bloccit!

{:.center}
![]({{ site.baseurl }}/img/reddit.svg)

Bloccit is an app that I built that's based on the fan fave Reddit, "*the front page of the internet*".

Users can sign up and sign in to get access to all the topics. Then, they can post on the the topic of their choosing, and just like at Reddit, the posts get up-votes and down-votes, with the highest voted posts displaying first.

Another ability users have is to comment on posts. Users can choose to *favorite* posts, and be notified by email when there are any new comments on those posts.

Bloccit uses a ranking algorithm that's similar to Reddit's, making sure that the best and most popular posts display first, but decrease slowly in rank over time.

To keep the most popular **current** posts at the top, I made the ranking method as follows:

{% highlight ruby %}
class Post < ApplicationRecord
  has_many :votes
{% endhighlight %}

{% highlight ruby %}
def points
  votes.sum(:value)
end
{% endhighlight %}

{% highlight ruby %}
def update_rank
  age_in_days = (created_at - Time.new(1970,1,1)) / 1.day.seconds
  new_rank = points + age_in_days
  update_attribute(:rank, new_rank)
end
{% endhighlight %}

This way you don't have high rated posts from 10 years ago still showing up at the top.


[Check out the app in production!](https://salty-plains-24479.herokuapp.com/)

Wanna see the code?

[Bloccit on Github](https://github.com/svancott/bloccit)
