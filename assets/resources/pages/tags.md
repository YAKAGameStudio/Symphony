---
permalink: /tags/
title: Tags
excerpt: Browse content by Tag
image: /assets/images/illustrations/news.png
---

{% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}

<!-- Content -->
<main class="p-3" aria-label="Content">
    <section class="container">
    {% for tag in site.tags %}
        <h3>{{ tag | first }}</h3>
        <div class="row row-cols-1 row-cols-md-3">
            {% for page in tag.last %}
            <div class="col">
                <div class="card text-dark bg-light h-100">
                    <img src="{{ page.image | absolute_url }}" class="card-img-top" alt="{{ page.title }}">
                    <div class="card-body">
                        <h5 class="card-title">{{ page.title }}</h5>
                        <h6 class="card-subtitle mb-2 text-muted">{{ page.date | date_to_string }}</h6>
                        <p class="card-text">{{ page.excerpt | strip_html | truncatewords: 20 }}</p>
                        {% if page.categories %}
                        <div>
                            <ul id="categories" class="nav">
                            {% for category in page.categories %}
                                <li class="nav-item mx-1 badge bg-primary">{{ category }}</li>
                            {% endfor %}
                            </ul>
                        </div>
                        {% endif %}
                    </div>
                    <div class="card-footer text-muted text-end">
                        <a href="{{ page.url | absolute_url }}" class="btn btn-primary" title="Read {{ page.title }}">Read More</a>
                    </div>
                </div>
            </div>
            {% endfor %}
        </div>
    {% endfor %}
    </section>
</main>