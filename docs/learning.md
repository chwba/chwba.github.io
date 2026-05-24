---
layout: page
title: Learning
permalink: /learning/
---

<div class="home">

{% assign sorted = site.learning | sort: "date" | reverse %}

  <ul class="post-list">

    {% for post in sorted %}
      <li>
        <span class="post-meta">
          {{ post.date | date: "%b %-d, %Y" }}
        </span>
        {% if post.public == false %}
          <span class="post-meta">(private)</span>
        {% endif %}
        <h4>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title }}
          </a>
        </h4>
        {% if post.tags %}
          <b class="post-tags">
            {% for tag in post.tags %}
              <span class="tag">#{{ tag }}</span>
            {% endfor %}
          </b>
        {% endif %}
        {% if post.excerpt %}
          {{ post.excerpt }}
        {% endif %}
      </li>
    {% endfor %}

  </ul>

</div>