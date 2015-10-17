---
layout: page
title: Podcast
permalink: /podcast/
---

Subscribe to *Grownups Read Things They Wrote as Kids* in:

- [iTunes / Apple Podcasts](http://links.grownupsreadthingstheywroteaskids.com/itunes)
- [SoundCloud](http://links.grownupsreadthingstheywroteaskids.com/soundcloud)
- [Overcast](http://links.grownupsreadthingstheywroteaskids.com/overcast)
- [Stitcher](http://links.grownupsreadthingstheywroteaskids.com/stitcher)
- [Pocket Casts](http://pcasts.in/feed/feeds.grownupsreadthingstheywroteaskids.com/podcast/)
- [TuneIn](http://links.grownupsreadthingstheywroteaskids.com/tunein)
- anywhere else using our [RSS feed](http://feeds.grownupsreadthingstheywroteaskids.com/podcast/)

Or [listen to past episodes in our show archives](http://www.grownupsreadthingstheywroteaskids.com/category/podcast/episodes/) or in the player below:

<!-- <iframe width="100%" height="450" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/playlists/127234644&amp;color=f37749&amp;auto_play=false&amp;hide_related=false&amp;show_comments=true&amp;show_user=true&amp;show_reposts=false" data-origwidth="100%" data-origheight="450" style="width: 598px;"></iframe> -->






{% for post in site.posts if post.categories contains 'episodes' %}
<div class="post">
<h1 class="post-title">
  <a href="{{ post.url }}">
    {{ post.title }}
  </a>
</h1>
<span class="post-date">{{ post.date | date_to_string }}</span>

<iframe width="100%" height="166" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/{{ post.soundcloud_id }}&amp;color=f37749&amp;auto_play=false&amp;hide_related=false&amp;show_comments=false&amp;show_user=true&amp;show_reposts=false"></iframe>
</div>
{% endfor %}


<div class="pagination">
  {% if paginator.next_page %}
    <a class="pagination-item older" href="{{ site.baseurl }}page{{paginator.next_page}}">Older</a>
  {% else %}
    <span class="pagination-item older">Older</span>
  {% endif %}
  {% if paginator.previous_page %}
    {% if paginator.page == 2 %}
      <a class="pagination-item newer" href="{{ site.baseurl }}">Newer</a>
    {% else %}
      <a class="pagination-item newer" href="{{ site.baseurl }}page{{paginator.previous_page}}">Newer</a>
    {% endif %}
  {% else %}
    <span class="pagination-item newer">Newer</span>
  {% endif %}
</div>