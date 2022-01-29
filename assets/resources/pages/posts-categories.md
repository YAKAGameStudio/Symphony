---
permalink: /topics/
title: Topics
excerpt: Browse content by Topic
image: illustrations/news.png
---
<!-- Content -->
<main class="p-3" aria-label="Content">
    <section class="container">
        <div class="row row-cols-1 row-cols-md-3">
            {% assign filteredPages = site.pages | where: "layout", "category" %}
            {% for item in filteredPages %}
            {% include /snippets/card.html %}
            {% endfor %}
        </div>
    </section>
</main>