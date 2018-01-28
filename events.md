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

{% if jekyll.environment == "development" %}
  <script>TitoDevelopmentMode = true</script>
{% endif %}

{% if site.data.events.upcoming %}
  {% assign upcoming = site.data.events.upcoming | sort: "date" %}
{% endif %}

{% assign past = site.data.events.past | sort: "date" | reverse %}

{% if upcoming %}

{% for event in upcoming %}

## <a name="{{ event.venue.city }}"></a>{{ event.venue.city }}, {{ event.venue.province }} {% if event.showtimes.size > 1 %} ({{ event.showtimes.size }} shows){% endif %}

{{ event.date | date: "%A, %B %-d, %Y" }} at <a href="{{ event.venue.url }}"> {{ event.venue.name }}</a> ({{ event.venue.address }})

{% if event.showtimes == nill and event.special != "Yes" %}We've scheduled this show, but reader signup and tickets are not available yet. For a heads-up, [join the newsletter](http://www.grownupsreadthingstheywroteaskids.com/mailing-list/).{% endif %}

{% for showtime in event.showtimes %}

#### {{ showtime.name }}




<ul class="fa-ul">
  {% if showtime.releases.general_admission contains "http" %}
    <li><i class="fa-li fa fa-ticket"></i><a href="{{ showtime.releases.general_admission }}">Buy audience tickets for {{ event.venue.city }}</a></li>
  {% else %}
    <li><i class="fa-li fa fa-ticket"></i><a href="https://ti.to/{{ event.tito_event }}/with/{{ showtime.releases.general_admission }}">Buy audience tickets for {{ event.venue.city }}</a></li>
  {% endif %}

  {% if showtime.releases.reader == nill %}
    <li><i class="fa-li fa fa-user-plus"></i>Reader signup details coming soon...</li>
  {% else %}
    <li><i class="fa-li fa fa-user-plus"></i><a href="https://ti.to/{{ event.tito_event }}/with/{{ showtime.releases.reader }}">Sign up to read in {{ event.venue.city }}</a></li>

  {% endif %}

</ul>

<small>{{ event.notes }}</small>

<script type="application/ld+json">
{
  "@context": "http://schema.org",
  "@type": "Event",
  "name": "Grownups Read Things They Wrote as Kids {{ event.venue.city }} - {{ showtime.name }}",
  "startDate" : "{{ event.date | date: "%F" }}",
  "url" : "{{ site.url }}{{ page.url }}",
  "location" : {
    "@type" : "Place",
    "sameAs" : "{{ event.venue.url }}",
    "name" : "{{ event.venue.name }}",
    "address" : "{{ event.venue.address }}"
  },
  "offers":{
      "@type": "Offer",
      "url" : "https://ti.to{{ event.tito_event }}",
      "price" : 14,
      "priceCurrency" : "CAD"
    }
}
</script>


{% endfor %}


<hr>
{% endfor %}

{% else %}

No upcoming events scheduled, but stay tuned. If you'd like a heads-up about upcoming shows, [join the email newsletter](https://grownupsreadthingstheywroteaskids.com/newsletter/):

{% include newsletter_subscribe.html %}

***

{% endif %}


# Ticketing questions?

We’ve tried to make GRTTWaK tickets as simple and straightforward as possible. Here are some [frequently asked questions](/faq/) about tickets (including answers). If you have a question that’s not answered here, [get in touch](/contact/).


# Past events

| Date          | City          | Venue  |
| ------------- |:-------------:| :-----:|
{% for event in past %}{{ event.date | date: "%B %-d, %Y" }} | {{ event.venue.city }} | {{ event.venue.name }} |
{% endfor %}