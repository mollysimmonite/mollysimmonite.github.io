---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
You can also find my articles on <a href="{{author.googlescholar}}">my Google Scholar profile</a>.
{% endif %}

{% include base_path %}

{% assign pubs = site.publications | sort: 'date' | reverse %}
{% assign current_year = "" %}
{% for pub in pubs %}
  {% assign pub_year = pub.date | date: "%Y" %}
  {% if pub_year != current_year %}
    {% assign current_year = pub_year %}

## {{ current_year }}

  {% endif %}
[{{ pub.title }}]({{ pub.url | relative_url }}) *{{ pub.venue }}*
{: .pub-entry}

{% endfor %}
