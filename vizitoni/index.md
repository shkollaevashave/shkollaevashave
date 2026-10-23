---
title: Vizitoni
intro: "[Si duket një vizitë: sa zgjat, çfarë përfshin, a ka guidë.]"
---

{% include hours.html %}

## Si të vini

{{ site.data.info.address.street }}, {{ site.data.info.address.city }}

[Udhëzime: parkimi, autobusi, në këmbë nga qendra.]

[Hapeni në Google Maps]({{ site.data.info.map_link }})

{% if site.data.info.map_embed != "" %}
<iframe class="map" src="{{ site.data.info.map_embed }}" loading="lazy" title="Harta"></iframe>
{% endif %}

## Aksesueshmëria

[A ka shkallë? A mund të hyjë një karrocë? Kjo pyetje bëhet shpesh.]
