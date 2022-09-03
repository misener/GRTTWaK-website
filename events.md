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

{% assign upcoming = site.events_upcoming | sort: "show_date" %}

{% if upcoming.size > 0 %}

# Upcoming events

| Date          | City          | Venue  | <i class="fa fa-ticket" aria-hidden="true"></i>  |
| ------------- |:-------------:| :-----:| :-----------------------------------------------:| :-----------------------------------------------:|
{% for event in upcoming %}{{ event.show_date | date: "%B %-d, %Y" }} | {{ event.venue.city }} | {{ event.venue.name }} | [More information]({{ event.url }})
{% endfor %}

{% else %}

No upcoming events scheduled, but stay tuned. If you'd like a heads-up about upcoming shows, [join the email newsletter](https://grownupsreadthingstheywroteaskids.com/newsletter/):

{% include newsletter_subscribe.html %}

***

{% endif %}

# Ticketing questions?

We’ve tried to make GRTTWaK tickets as simple and straightforward as possible. Here are some [frequently asked questions](/faq/) about tickets (including answers). If you have a question that’s not answered here, [get in touch](/contact/).

# Past Events

{% assign past = site.events_past | sort: "show_date" | reverse %}


| Date          | City          | Venue  |
| ------------- |:-------------:| :-----:| :-----------------------------------------------:|
{% for event in past %}{{ event.show_date | date: "%B %-d, %Y" }} | {{ event.venue.city }} | {{ event.venue.name }} |
{% endfor %}


# Past events

{% assign old_past = site.data.events.past | sort: "date" | reverse %}

| Date          | City          | Venue  |
| ------------- |:-------------:| :-----:|
{% for event in old_past %}{{ event.date | date: "%B %-d, %Y" }} | {{ event.venue.city }} | {{ event.venue.name }} |
{% endfor %}




{% if jekyll.environment == "development" %}
  <script>TitoDevelopmentMode = true</script>
{% endif %}