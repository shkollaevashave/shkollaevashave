---
title: Kontakt
---
{%- assign i = site.data.info %}

**Email:** [{{ i.email }}](mailto:{{ i.email }})
{% if i.phone != "" %}
**Telefon:** [{{ i.phone }}](tel:{{ i.phone | remove: ' ' }})
{% endif %}
**Adresa:** {{ i.address.street }}, {% if i.address.postcode != "" %}{{ i.address.postcode }} {% endif %}{{ i.address.city }}

Për udhëtime shkollore, shihni [faqen e rezervimeve](/udhetime-shkollore/).

{% include hours.html %}
