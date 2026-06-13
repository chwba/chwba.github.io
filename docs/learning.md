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

        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>

        {% if post.tags %}
          <p>
            {% for tag in post.tags %}
              <b><i>#{{ tag }}</i></b>
            {% endfor %}
          </p>
        {% endif %}

        {% if post.excerpt %}
          {{ post.excerpt }}
        {% endif %}

      </li>

    {% endfor %}

  </ul>

</div>