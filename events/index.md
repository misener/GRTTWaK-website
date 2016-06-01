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
 
## <a name="{{ event.venue.city }}"></a>{{ event.venue.city }}{% if event.showtimes.size > 1 %} ({{ event.showtimes.size }} shows){% endif %}

{{ event.date | date: "%A, %B %-d, %Y" }} at <a href="{{ event.venue.url }}"> {{ event.venue.name }}</a> ({{ event.venue.address }})

{% if event.showtimes == nill %}We've announced this show, but reader signup and tickets are not available yet. For a heads-up, [join the newsletter](http://www.grownupsreadthingstheywroteaskids.com/mailing-list/).{% endif %}

{% for showtime in event.showtimes %}
{% if event.showtimes.size > 1 %}### {{ showtime.name }}
{% endif %}

{% comment %}
<tito-button event="{{ event.tito_event }}" releases="{{ showtime.releases.reader }}"><i class="fa fa-user-plus"></i> Sign up to read in {{ event.venue.city }}</tito-button> 

[Sign up to read in {{ event.venue.city }}](https://ti.to/{{ event.tito_event }}/with/{{ showtime.releases.reader }})
{% endcomment %}

<button onclick="window.location='https://ti.to/{{ event.tito_event }}/with/{{ showtime.releases.reader }}';"><i class="fa fa-user-plus"></i> Sign up to read in {{ event.venue.city }}</button> <tito-button event="{{ event.tito_event }}" releases="{{ showtime.releases.general_admission }}"><i class="fa fa-ticket"></i> Buy tickets</tito-button>

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
      "price" : 12,
      "priceCurrency" : "CAD"
    }
}
</script>


{% endfor %}

<hr>
{% endfor %}

{% else %}

No upcoming events scheduled, but stay tuned. If you'd like a heads-up about upcoming shows, [join the email newsletter](https://grownupsreadthingstheywroteaskids.com/newsletter/):

<form action="https://sendy.grownupsreadthingstheywroteaskids.com/subscribe" method="POST" accept-charset="utf-8" class="pure-form pure-form-aligned">
  <fieldset>
  <div class="pure-control-group">
    <label for="name">Name</label>
    <input type="text" name="name" id="name" placeholder="Name">
  </div>

  <div class="pure-control-group">
    <label for="email">Email</label>
    <input type="text" name="email" id="email" placeholder="your@email.com">
  </div>

  <div class="pure-control-group">
   <label for="City">City</label>
   <input type="text" name="City" id="City" placeholder="City">
  </div>

  <div class="pure-controls">
   <button type="submit" class="pure-button pure-button-primary" name="submit" id="submit" style="background-color: #f37749;">Submit</button>
  </div>

    <input type="hidden" name="list" value="etW6B40hkAJ4FkY9FvApEQ">

  </fieldset>
</form>

***

{% endif %}





## Past events

| Date          | City          | Venue  |
| ------------- |:-------------:| :-----:|
{% for event in past %}{{ event.date | date: "%B %-d, %Y" }} | {{ event.venue.city }} | {{ event.venue.name }} |
{% endfor %}