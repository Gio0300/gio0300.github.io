---
layout: default
---
{% for post in site.posts %}
  <article>
      
    <h2 class="post-title"><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <h3 class="post-subtitle"><a href="{{ post.url }}">{{ post.subtitle }}</a></h3>
    
    <time datetime="{{ post.date }}">{{ post.date | date: site.date_format}}</time>
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