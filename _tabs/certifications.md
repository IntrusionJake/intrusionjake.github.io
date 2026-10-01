---
# Content is driven by _data/certs.yml, so add new certs there.
icon: fas fa-certificate
excerpt_separator: "<!--more-->"
order: 5
---

{% assign groups = "earned,in-progress,planned" | split: "," %}
{% for status in groups %}
  {% assign certs = site.data.certs | where: "status", status %}
  {% if certs.size > 0 %}

{% case status %}
{% when "earned" %}
## <i class="fas fa-award"></i> Earned
{% when "in-progress" %}
## <i class="fas fa-spinner"></i> In Progress
{% else %}
## <i class="far fa-calendar"></i> On the Roadmap
{% endcase %}

| Certification | Issuer | Date | Links |
| :--- | :--- | :--- | :--- |
{% for c in certs -%}
| **{{ c.name }}** | {{ c.issuer }} | {{ c.date | default: "—" }} | {% if c.post %}[Write-up]({{ c.post | relative_url }}){% endif %}{% if c.post and c.verify %} · {% endif %}{% if c.verify %}[Verify]({{ c.verify }}){% endif %}{% unless c.post or c.verify %}—{% endunless %} |
{% endfor %}

  {% endif %}
{% endfor %}
