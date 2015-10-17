---
layout: default
title: Home
---

![GRTTWaK](/images/end-of-world-DSCF4444-800px.jpg)

Since 2007, *Grownups Read Things They Wrote as Kids* has invited audiences to remember the good, the bad, and the awkward parts of growing up. Courageous adults read their childhood and teenage diaries, poetry, short stories, letters from camp, and much more... out loud in front of an audience.

## Live Events

{% if site.data.events.upcoming.size > 0 %}
{% assign upcoming = site.data.events.upcoming %}
We have upcoming live events in: {% for event in upcoming %}<a href="{{ event.tickets.url }}">{{ event.venue.city }}</a>, {% endfor %} and beyond...

{% else %}

NO EVENTS!

{% endif %}

## Latest Episode
{% for post in site.posts if post.categories contains 'episodes' limit:1 %}
<iframe width="100%" height="166" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/{{ post.soundcloud_id }}&amp;color=f37749&amp;auto_play=false&amp;hide_related=false&amp;show_comments=false&amp;show_user=true&amp;show_reposts=false"></iframe>
{% endfor %}

[More episodes](/podcast/)