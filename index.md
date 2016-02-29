---
layout: default
title: Home
---

## <i class="fa fa-headphones"></i> Latest Episode: {% for post in site.posts if post.categories contains 'episodes' limit:1 %}{{ post.city }}{% endfor %}

{% for post in site.posts if post.categories contains 'episodes' limit:1 %}
{% if post.soundcloud_id %}
<iframe width="100%" height="166" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/{{ post.soundcloud_id }}&amp;color=f37749&amp;auto_play=false&amp;hide_related=false&amp;show_comments=false&amp;show_user=true&amp;show_reposts=false"></iframe>
{% elsif post.simplecast_episode_id %}
[<img src="/images/episodes/{{ post.number }}.jpg">]({{ post.url }})
<iframe frameborder='0' height='36px' scrolling='no' seamless src='https://simplecast.com/e/{{ post.simplecast_episode_id }}?style=dark' width='100%'></iframe>

{{ post.excerpt}}

{% endif %}
{% endfor %}

<i class="fa fa-headphones"></i> [Listen to more episodes...](/podcast/)

## <i class="fa fa-calendar"></i> Live Events 

{% if site.data.events.upcoming.size > 0 %}
{% assign upcoming = site.data.events.upcoming %}
We have upcoming live events in: {% for event in upcoming %}<a href="/events/#{{ event.venue.city }}">{{ event.venue.city }}</a>, {% endfor %} and beyond...

{% else %}

NO EVENTS!

{% endif %}

## About

Since 2007, *Grownups Read Things They Wrote as Kids* has invited audiences to remember the good, the bad, and the awkward parts of growing up. Courageous adults read their childhood and teenage diaries, poetry, short stories, letters from camp, and much more... out loud in front of an audience. [Learn more...](/about/)