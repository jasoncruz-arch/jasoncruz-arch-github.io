---
layout: page
title: Writings
permalink: /writings/
---

<div class="post-list">
  {% for post in site.posts %}
    <article class="post-item">
      <a href="{{ post.url | relative_url }}">
        <img class="post-thumbnail" src="{{ post.thumbnail | default: '/assets/images/default-essay-thumb.jpg' }}" alt="{{ post.title | escape }} thumbnail">
      </a>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      <div class="post-meta-row">
        {% if post.tags %}
          {% for tag in post.tags %}
            <a class="post-tag" href="?tag={{ tag | uri_escape }}">{{ tag }}</a>{% unless forloop.last %}, {% endunless %}
          {% endfor %}
        {% endif %}
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
      </div>
      <div class="post-description">
        {{ post.excerpt | strip_html | truncatewords: 30 }}
        <br> <br>
      <a href="{{ post.url | relative_url }}" class="read-more-link">
          Read more <span class="arrow">&rarr;</span>
      </a>
      </div>
    </article>
  {% endfor %}
</div>


<script>
  // Helper: Get the value of 'tag' from URL query string
  function getQueryParam(param) {
    const params = new URLSearchParams(window.location.search);
    return params.get(param);
  }

  const selectedTag = getQueryParam('tag');

  if (selectedTag) {
    // Find all posts on the page
    const posts = document.querySelectorAll('.post-item');

    posts.forEach(post => {
      // Gather all tags in this post (with class 'post-tag')
      const tags = Array.from(post.querySelectorAll('.post-tag')).map(el => el.textContent.trim());

      // Show post only if it includes selectedTag, else hide it
      if (tags.includes(selectedTag)) {
        post.style.display = '';
      } else {
        post.style.display = 'none';
      }
    });
  }
</script>

