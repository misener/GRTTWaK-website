---
layout: page
title: Newsletter
redirect_from:
  - /mailing-list/

---

Our email newsletter is the first place we announce new live events. Sign up!

{% include newsletter_subscribe.html %}

<script type="text/javascript">
var hashParams = window.location.hash.substr(1).split('&');
for(var i = 0; i < hashParams.length; i++){
    var p = hashParams[i].split('=');
    document.getElementById(p[0]).value = decodeURIComponent(p[1]);;
}
</script>