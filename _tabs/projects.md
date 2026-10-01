---
# Hidden until there's something to show: set to true to add the page + sidebar tab.
published: false
# Content is driven by _data/projects.yml, so add new projects there.
icon: fas fa-code
order: 4
excerpt_separator: "<!--more-->"
---

Things I've built, broken and fixed: labs, tools and scripts.

<div class="row g-3 mt-1">
{% for p in site.data.projects %}
  <div class="col-12 col-lg-6">
    <div class="card h-100">
      <div class="card-body d-flex flex-column">
        <h3 class="card-title h5 mt-0 mb-2">
          {{ p.name }}
          {% if p.status %}<span class="badge text-bg-secondary ms-1 fw-normal small">{{ p.status }}</span>{% endif %}
        </h3>
        <p class="card-text mb-2">{{ p.description }}</p>
        {% if p.tags %}
        <p class="mb-2">{% for t in p.tags %}<code class="me-1">{{ t }}</code>{% endfor %}</p>
        {% endif %}
        <div class="mt-auto">
          {% if p.repo %}<a href="{{ p.repo }}" class="me-3"><i class="fab fa-github"></i> Code</a>{% endif %}
          {% if p.demo %}<a href="{{ p.demo }}" class="me-3"><i class="fas fa-up-right-from-square"></i> Demo</a>{% endif %}
          {% if p.post %}<a href="{{ p.post | relative_url }}"><i class="fas fa-book-open"></i> Write-up</a>{% endif %}
        </div>
      </div>
    </div>
  </div>
{% endfor %}
</div>
