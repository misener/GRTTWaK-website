---
layout: default
title: Home
---


  <!-- Load Facebook SDK for JavaScript -->
  <div id="fb-root"></div>
  <script>(function(d, s, id) {
    var js, fjs = d.getElementsByTagName(s)[0];
    if (d.getElementById(id)) return;
    js = d.createElement(s); js.id = id;
    js.src = "//connect.facebook.net/en_US/sdk.js#xfbml=1&version=v2.6";
    fjs.parentNode.insertBefore(js, fjs);
  }(document, 'script', 'facebook-jssdk'));</script>

  <!-- Your embedded video player code -->


{% comment %}
  {% for post in site.posts if post.categories contains 'episodes' limit:1 %}

  <!-- [<img src="/images/episodes/{{ post.number }}.jpg">]({{ post.url }}) -->

  <!-- <iframe frameborder="0" height="36px" scrolling="no" src="https://simplecast.com/e/{{ post.simplecast_episode_id }}?style=dark" width="100%"></iframe>
   -->

  ## Latest podcast episode: {% for post in site.posts if post.categories contains 'episodes' limit:1 %}[{{ post.city }}]({{ post.url }}){% endfor %}

  <!-- <iframe src="https://art19.com/shows/grownups-read-things-they-wrote-as-kids/episodes/{{ post.art19_id }}/embed?theme=dark-custom&primary_color=%23f37749" style="width: 100%; height: 200px; border: 0 none;" scrolling="no"></iframe> -->

  <iframe frameborder="no" height="200" scrolling="no" src="https://player.megaphone.fm/{{ post.megaphone_uid }}?sharing=false" width="100%"></iframe>

  <!-- <div id="episodes-page-{{ page.number }}"
       class="art19-web-player awp-medium awp-theme-dark-custom"
       data-episode-id="{{ post.art19_id }}"
       data-primary-color="#f37749"
       data-emit-events="true"
  	 data-bt-series-id="a160bd44-67e2-11e7-b61d-0e6e2408d686"
  	 data-bt-guid={% if post.guid %}"{{ post.guid }}"{% else %}"{{ post.art19_id }}"{% endif %}
       data-bt-episode-title="{{ post.number }}: &quot;{{ post.quote }}&quot; ({{ post.city }})"
       data-bt-episode-author="Grownups Read Things They Wrote as Kids"
       ></div> -->

  {{ post.excerpt}}
  {% endfor %}

{% endcomment %}


<iframe frameborder="no" src="https://playlist.megaphone.fm?p=GUR5294085005&sharing=false" width="100%" height="482"></iframe>

Listen in your [favourite podcast app](/podcast/):

<a href="https://podcasts.apple.com/podcast/id890900960?mt=2&at=10lR7u&ct=website_front_page_badge"><img src="//linkmaker.itunes.apple.com/assets/shared/badges/en-us/podcast-lrg.svg" style="display:inline" height="55px"></a> <!-- <a href="https://podcasts.google.com/?feed=aHR0cDovL2ZlZWRzLmdyb3dudXBzcmVhZHRoaW5nc3RoZXl3cm90ZWFza2lkcy5jb20vcG9kY2FzdA"><img src="/images/google_podcasts.png" style="display:inline" height="55px"></a> --> <a href="https://open.spotify.com/show/0tKu6eD6VDfxboZoWd0j6H"><img src="/images/spotify-podcast-badge-blk-grn-330x80.svg" height="55px" style="display:inline"></a>  <a href="https://pca.st/grttwak"><img src="https://static2.pocketcasts.com/assets/subscribe/pocketcasts_medium_dark@2x.png" style="display:inline" height="55px"></a> <!--<a href="https://play.radiopublic.com/2f14f380-2584-47a6-acac-d937f60121fd?utm_source=GRTTWaK&utm_medium=grttwak-website&utm_campaign=grttwak-frontpage"><img src="/images/radiopublic_badge.png" height="59px" style="display:inline"></a>--> <!-- <a href="https://www.podbean.com/podcast-detail/e5yin-338c7/"><img style="display:inline" height="59px" src="//d8g345wuhgd7e.cloudfront.net/site/images/badges/w600.png"></a> -->

{% comment %}
## <i class="fa fa-heart" aria-hidden="true"></i> Support the show

*Grownups Read Things They Wrote as Kids* is an independent production, supported by people who love it. <a href="/support/">Become a patron today</a>.
{% endcomment %}


## Live Events 

{% assign upcoming = site.events_upcoming | sort: "show_date" %}

{% if upcoming.size > 0 %}

<!-- Check out a list of <a href="/events/">our upcoming live events</a>! -->

We have upcoming live events in {% for item in upcoming %}<a href="{{ item.url }}">{{ item.venue.city }}</a>, {% endfor %} and beyond...

{% else %}

No upcoming events scheduled, but stay tuned. If you'd like a heads-up about upcoming shows, [join the email newsletter](https://grownupsreadthingstheywroteaskids.com/newsletter/):

{% include newsletter_subscribe.html %}

{% endif %}

## Video
We post new reader videos **every weekday** on [Facebook](https://www.facebook.com/pg/grownupsreadthingstheywroteaskids/videos/).

<div class="fb-video" data-href="https://www.facebook.com/grownupsreadthingstheywroteaskids/videos/10154847272218600/" data-width="auto" data-show-text="false"><blockquote cite="https://www.facebook.com/grownupsreadthingstheywroteaskids/videos/10154847272218600/" class="fb-xfbml-parse-ignore"><a href="https://www.facebook.com/grownupsreadthingstheywroteaskids/videos/10154847272218600/">&quot;I&#039;m pretty sure I missed his lips&quot;</a><p>When Jeanna was 12, she had her first kiss with a boy named Tyler. She may have missed his lips.</p>Posted by <a href="https://www.facebook.com/grownupsreadthingstheywroteaskids/">Grownups Read Things They Wrote as Kids</a> on Monday, April 24, 2017</blockquote></div>

{% comment %}
## About

Since 2007, *Grownups Read Things They Wrote as Kids* has invited audiences to remember the good, the bad, and the awkward parts of growing up. Courageous adults read their childhood and teenage diaries, poetry, short stories, letters from camp, and much more... out loud in front of an audience. [Learn more...](/about/)
{% endcomment %}