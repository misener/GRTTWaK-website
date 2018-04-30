---
layout: page
title: Live Events
permalink: /events/index.html
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

<script>fbq('track', 'ViewContent');</script>

![GRTTWaK](/images/charlottetown_pano.jpg)



{% if site.events-upcoming %}
  {% assign upcoming = site.events-upcoming | sort: "date" %}
{% endif %}


{% assign past = site.data.events.past | sort: "date" | reverse %}

{% if upcoming %}

## Upcoming events

| Date          | City          | Venue  | Details |
| ------------- |:-------------:| :-----:| :------:|
{% for event in upcoming %}{{ event.date | date: "%B %-d, %Y" }} | {{ event.venue.city }} | {{ event.venue.name }} | <a href="{{ event.url }}">Get tickets or sign up to read</a>
{% endfor %}

{% else %}

No upcoming events scheduled, but stay tuned. If you'd like a heads-up about upcoming shows, [join the email newsletter](https://grownupsreadthingstheywroteaskids.com/newsletter/):

{% include newsletter_subscribe.html %}

***

{% endif %}


## Ticketing questions?

We’ve tried to make GRTTWaK tickets as simple and straightforward as possible. Here are some [frequently asked questions](/faq/) about tickets (including answers). If you have a question that’s not answered here, [get in touch](/contact/).


## Past events

| Date          | City          | Venue  |
| ------------- |:-------------:| :-----:|
{% for event in past %}{{ event.date | date: "%B %-d, %Y" }} | {{ event.venue.city }} | {{ event.venue.name }} |
{% endfor %}


{% if jekyll.environment == "development" %}
  <script>TitoDevelopmentMode = true</script>
{% endif %}
