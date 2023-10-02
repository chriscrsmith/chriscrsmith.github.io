---
layout: page
title: Publications
permalink: /publications
---

##### [Google scholar](https://scholar.google.com/citations?user=ZHHGVn8AAAAJ&hl=en)

## Publications

{% assign mainpubs = site.publications | where_exp:"pub", "pub.year > 2010" | sort: "year" | reverse %}

{% for pub in mainpubs %}
{% if pub.journal %}

<i>{{ pub.title }}</i><span style="color: grey;">, by</span>
{{ pub.authors }}<span style="color: grey;">, in</span>
{{ pub.journal }}, {{ pub.year }}.
{: .pubcite}

{% if pub.content %}
<div class="refdesc">
{{ pub.content | markdownify }}
</div>
{% endif %}

<div class="pubrefs">
{% if pub.preprint %}
<a href="{{ pub.preprint }}" class="preprint">preprint</a>
{% endif %}
{% if pub.link %} ||
<a href="{{ pub.link }}" class="journal">journal</a>
{% endif %}
{% if pub.github %} ||
<a href="{{ pub.github }}" class="github">code</a>
{% endif %}
</div>

{% endif %}
{% endfor %}

