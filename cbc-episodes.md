---
layout: page
title: CBC Episodes
redirect_from: 
  - /2014/08/episode-10-montreal/
  - /2014/08/episode-9-ottawa/
  - /2014/08/episode-7-winnipeg/
  - /2014/07/episode-6-fredericton/
  - /2014/07/episode-5-halifax/
  - /2014/07/episode-4-regina/
  - /2014/07/episode-3-st-johns/
  - /2014/07/episode-2-calgary/
  - /2014/06/episode-1-vancouver/
---

In the summer of 2014, CBC Radio aired 10 episodes of GRTTWaK. They're not on the CBC website any more, but we've collected them here for posterity.

{% assign episodes = site.data.cbc-episodes  %}

{% for episode in episodes %}
## Episode {{ episode.number }}: {{ episode.city }}

<audio controls>
	<source src="{{ episode.mp3_url }}" type="audio/mpeg">
	Your browser does not support the audio element.
</audio>

[MP3]({{ episode.mp3_url }})

***

{% endfor %}