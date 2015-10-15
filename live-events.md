---
layout: page
title: Live Events
permalink: /events/
redirect_from:
  - /liveshows/
  - /event/grttwak-halifax/
  - /event/grttwak-regina/
  - /event/grttwak-calgary/
  - /event/grttwak-vancouver/
  - /event/grttwak-winnipeg/
  - /event/grttwak-toronto-grttwak-radio-launch-party/
  - /event/grttwak-st-johns/
  - /event/grttwak-ottawa/
  - /event/grttwak-fredericton/
  - /event/grttwak-montreal/
  - /event/grttwak-toronto/
  - /event/grttwak-montreal-2/
  - /event/grttwak-windsor/
  - /event/grttwak-ottawa-2/
  - /event/grttwak-toronto-2/
  - /event/banff/
  - /event/grttwak-calgary-2/
  - /event/grttwak-hamilton/
  - /event/grttwak-victoria/
  - /event/grttwak-vancouver-2/
  - /event/grttwak-windsor-2/
  - /event/grttwak-detroit/
  - /event/grttwak-toronto-3/
  - /event/grttwak-toronto-4/
  - /event/grttwak-halifax-3/
  - /event/grttwak-charlottetown/
  - /event/grttwak-st-johns-2/
  - /event/grttwak-winnipeg-2/
  - /event/grttwak-edmonton/
  - /event/grttwak-yellowknife/
  - /event/grttwak-calgary-3/
---


{% assign upcoming = site.data.events.upcoming | sort: "date" %}
{% assign past = site.data.events.past | sort: "date" | reverse %}

{% for event in upcoming %}
## {{ event.venue.city }}

{{ event.date | date: "%A, %B %-d, %Y" }} at <a href="{{ event.venue.url }}"> {{ event.venue.name }} </a> ({{ event.venue.address }})

<a href="{{ event.signup.url }}">Sign up to read in {{ event.venue.city }}</a>, or <a href="{{ event.tickets.url }}">buy tickets</a>.

<hr>
{% endfor %}



<!-- ## Upcoming

| Date          | Where         | Readers  | Audience |
| ------------- |:-------------:| :-----:  | :------: |
{% for event in upcoming %}{{ event.date | date: "%B %-d, %Y" }} |  {{ event.venue.city }} <br> <a href="{{ event.venue.url }}"> {{ event.venue.name }} </a> | <a href="{{ event.signup.url }}">Sign up to read</a> | <a href="{{ event.tickets.url }}">Buy tickets</a> |
{% endfor %} -->

## Past events

| Date          | City          | Venue  |
| ------------- |:-------------:| :-----:|
{% for event in past %}{{ event.date | date: "%B %-d, %Y" }} | {{ event.venue.city }} | {{ event.venue.name }} |
{% endfor %}
