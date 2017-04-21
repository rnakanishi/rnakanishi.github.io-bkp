---
layout: page
title: Blog
permalink: /blog/
---
Coming soon

{% for post in site.posts %}
        <p class="posted">{{ post.date | date_to_string }}  |  (10 )  Comments</p>
        <p><a href="{{ site.prefix }}{{ post.url }}">{{ post.excerpt | remove: '<p>' | remove: '</p>' }}</a></p>
{% endfor %}


<!-- This loops through the paginated posts -->
{% for post in site.posts %}
    <h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
  <p class="author">
    <span class="date">{{ post.date }}</span>
  </p>
  <div class="content">
    {{ post.content }}
  </div>
{% endfor %}

<!-- Pagination links -->
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}" class="previous">Previous</a>
  {% else %}
    <span class="previous">Previous</span>
  {% endif %}
  <span class="page_number ">Page: {{ paginator.page }} of {{ paginator.total_pages }}</span>
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}" class="next">Next</a>
  {% else %}
    <span class="next ">Next</span>
  {% endif %}
</div>
