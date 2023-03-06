---
layout: default
---
<h1 class="dashed_underline">Articles</h1>

{% for post in site.posts %}
  <article>
    <h2>
      <a href="{{ post.url }}">
        <h2 class="post-title">{{ post.title }}</h2>
        <h3 class="post-subtitle">{{ post.subtitle }}</h3>
      </a>
    </h2>
    <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
    <p>{{ post.excerpt }}</p>

    {% if site.feed_show_tags != false and post.tags.size > 0 %}
      <div class="blog-tags">
        <span>Tags:</span>
        <!-- role="list" needed so that `list-style: none` in Safari doesn't remove the list semantics -->
        <ul class="d-inline list-inline" role="list">
          {% for tag in post.tags %}
          <li class="list-inline-item">
            <a href="{{ '/tags' | absolute_url }}#{{- tag -}}">{{- tag -}}</a>
          </li>
          {% endfor %}
        </ul>
      </div>
      {% endif %}
  </article>
{% endfor %}