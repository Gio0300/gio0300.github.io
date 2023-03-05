---
layout: default
---
Hello and welcome to my blog. My name is Gio, I'm a professional computer geek and this is my blog. I hope you'll find the articles interesting or at the very least informative.

{% for post in site.posts %}
  <article>
    <h2>
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h2>
    <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
    {{ post.description }}
  </article>
{% endfor %}