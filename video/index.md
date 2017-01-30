---
layout: page
title: Video
---

Starting in 2017, as an experiment, we've recorded video at our live events.

{% assign past = site.data.events.past | sort: "date" | reverse %}

{% for event in past %}


{% for showtime in event.showtimes %}

{% if showtime.youtube %}

## {{ event.venue.city }} {% if event.showtimes.size > 1 %} -- {{ showtime.name }}{% endif %}

Recorded {{ event.date | date: "%A, %B %-d, %Y" }} at <a href="{{ event.venue.url }}"> {{ event.venue.name }}</a>
<iframe width="560" height="315" src="https://www.youtube.com/embed/{{ showtime.youtube }}" frameborder="0" allowfullscreen></iframe>

{% endif %}

{% endfor %}
{% endfor %}



