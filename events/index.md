---
layout: page
title: Live Events
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

{% comment %}

<tito-button event="{{ event.tito_event }}" releases="{{ showtime.releases.reader }}"><i class="fa fa-user-plus"></i> Sign up to read in {{ event.venue.city }}</tito-button>

{% if showtime.releases.general_admission contains "http" %}
  <button onclick="window.location='{{ showtime.releases.general_admission }}';"><i class="fa fa-ticket"></i> Buy tickets</button>
{% else %}
  <tito-button event="{{ event.tito_event }}" releases="{{ showtime.releases.general_admission }}"><i class="fa fa-ticket"></i> Buy tickets</tito-button>


{% endif %}

{% endcomment %}


<ul class="fa-ul">
  {% if showtime.releases.general_admission contains "http" %}
    <li><i class="fa-li fa fa-ticket"></i><a href="{{ showtime.releases.general_admission }}">Buy audience tickets for {{ event.venue.city }}</a></li>
  {% else %}
    <li><i class="fa-li fa fa-ticket"></i><a href="https://ti.to/{{ event.tito_event }}/with/{{ showtime.releases.general_admission }}">Buy audience tickets for {{ event.venue.city }}</a></li>
  {% endif %}

  <li><i class="fa-li fa fa-user-plus"></i><a href="https://ti.to/{{ event.tito_event }}/with/{{ showtime.releases.reader }}">Sign up to read in {{ event.venue.city }}</a></li>
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



# Ticketing FAQ

We've tried to make GRTTWaK tickets as simple and straightforward as possible. Here are a few answers to frequently asked questions. If you have a question that's not answered here, [get in touch](/contact/).

## <a name="waitlist"></a> It says you're sold out. Are you really sold out?

If you can't buy a ticket, we're probably sold out. We know this can be frustrating.

The first place we announce live shows is through our [email newsletter](https://grownupsreadthingstheywroteaskids.com/newsletter/). Often, live events fill up hours (or minutes) after they're announced.

Our ticketing company, [Tito](https://ti.to/), has a "waiting list" feature. If a show is sold out, you can join the waiting list. If more general admission tickets become available, we make them available to members of the waiting list. Joining the waiting list does not guarantee you a ticket, nor does it give you any special privileges for the *next* available show.

Reader signup and general admission tickets are first-come, first-served. It's not ideal for everyone, but it's the fairest way we know how to do it. We appreciate your patience. 

## <a name="reader_waitlist"></a> How does the reader waiting list work?

Reader signup is first-come, first-served. If all the reader spots are taken, you'll see an option that says "Join the Waiting List." If you add your name and email to the waiting list, and a reader spot opens up in the days or weeks leading up to an event, we'll be in touch by email. It might be very short notice.

Please note that a spot on the waiting list does not guarantee you a reading spot.

Remember — kid writing doesn't expire, and we're planning to keep doing shows well into the future.

## <a name="refunds"></a>Can I get a refund?

For most GRTTWaK events, General Admission tickets are fully transferrable to another person. Simply follow the links in the email confirmation from Tito. As a general rule, we can process refunds but only **up until one week before** a live event. We cannot accommodate last-minute refunds.

A small handful of GRTTWaK events are part of festivals. In cases like these where we don't directly control ticketing, refund and exchangepolicies may vary.


# Past events

| Date          | City          | Venue  |
| ------------- |:-------------:| :-----:|
{% for event in past %}{{ event.date | date: "%B %-d, %Y" }} | {{ event.venue.city }} | {{ event.venue.name }} |
{% endfor %}