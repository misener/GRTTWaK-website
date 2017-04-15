---
layout: default
title: Home
---

{% for post in site.posts if post.categories contains 'episodes' limit:1 %}

<!-- [<img src="/images/episodes/{{ post.number }}.jpg">]({{ post.url }}) -->

<!-- <iframe frameborder="0" height="36px" scrolling="no" src="https://simplecast.com/e/{{ post.simplecast_episode_id }}?style=dark" width="100%"></iframe>
 -->


## Latest podcast episode: {% for post in site.posts if post.categories contains 'episodes' limit:1 %}[{{ post.city }}]({{ post.url }}){% endfor %}

<iframe src="https://art19.com/shows/grownups-read-things-they-wrote-as-kids/episodes/{{ post.art19_id }}/embed?theme=dark-custom&primary_color=%23f37749" style="width: 100%; height: 200px; border: 0 none;" scrolling="no"></iframe>

{{ post.excerpt}}

{% endfor %}



<i class="fa fa-headphones"></i> [Listen to more episodes in the archives](/podcast/) or your favourite app:

<a href="https://itunes.apple.com/podcast/id890900960?mt=2&at=10lR7u&ct=website_front_page_badge"><img src="//linkmaker.itunes.apple.com/assets/shared/badges/en-us/podcast-lrg.svg" style="display:inline" height="59px"></a> <a href="http://links.grownupsreadthingstheywroteaskids.com/spotify"><img src="/images/spotify_logo.png" height="59px" style="display:inline"></a>

## <i class="fa fa-heart" aria-hidden="true"></i> Support the show

*Grownups Read Things They Wrote as Kids* is an independent production, supported by people who love it. <a href="/support/">Become a patron today</a>.

## <i class="fa fa-calendar"></i> Live Events 

{% if site.data.events.upcoming.size > 0 %}
{% assign upcoming = site.data.events.upcoming %}
We have upcoming live events in: {% for event in upcoming %}<a href="/events/#{{ event.venue.city }}">{{ event.venue.city }}</a>, {% endfor %} and beyond...

{% else %}

No upcoming events scheduled, but stay tuned. If you'd like a heads-up about upcoming shows, [join the email newsletter](https://grownupsreadthingstheywroteaskids.com/newsletter/):

{% include newsletter_subscribe.html %}

{% endif %}

## About

Since 2007, *Grownups Read Things They Wrote as Kids* has invited audiences to remember the good, the bad, and the awkward parts of growing up. Courageous adults read their childhood and teenage diaries, poetry, short stories, letters from camp, and much more... out loud in front of an audience. [Learn more...](/about/)