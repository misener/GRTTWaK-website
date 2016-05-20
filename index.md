---
layout: default
title: Home
---

## <i class="fa fa-headphones"></i> Latest Episode: {% for post in site.posts if post.categories contains 'episodes' limit:1 %}{{ post.city }}{% endfor %}

{% for post in site.posts if post.categories contains 'episodes' limit:1 %}

[<img src="/images/episodes/{{ post.number }}.jpg">]({{ post.url }})

<iframe frameborder="0" height="36px" scrolling="no" src="https://simplecast.com/e/{{ post.simplecast_episode_id }}?style=dark" width="100%"></iframe>

{{ post.excerpt}}

{% endfor %}

<i class="fa fa-headphones"></i> [Listen to more episodes in the archives](/podcast/) or subscribe:

<a href="https://itunes.apple.com/podcast/id890900960?mt=2&at=10lR7u&ct=website_front_page_badge"><img src="https://linkmaker.itunes.apple.com/images/badges/en-us/badge_itunes-lrg.svg" style="display:inline" height="59px"></a> <a href="http://links.grownupsreadthingstheywroteaskids.com/googleplay"><img src="/images/get_it_on_play_logo_large.png" style="display:inline"></a>

## <i class="fa fa-calendar"></i> Live Events 

{% if site.data.events.upcoming.size > 0 %}
{% assign upcoming = site.data.events.upcoming %}
We have upcoming live events in: {% for event in upcoming %}<a href="/events/#{{ event.venue.city }}">{{ event.venue.city }}</a>, {% endfor %} and beyond...

{% else %}

No  events scheduled, but stay tuned. If you'd like a heads-up about upcoming shows, [join the email newsletter](https://grownupsreadthingstheywroteaskids.com/newsletter/).

{% endif %}

## About

Since 2007, *Grownups Read Things They Wrote as Kids* has invited audiences to remember the good, the bad, and the awkward parts of growing up. Courageous adults read their childhood and teenage diaries, poetry, short stories, letters from camp, and much more... out loud in front of an audience. [Learn more...](/about/)