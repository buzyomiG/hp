
{% assign target_category = "裏話" %}
<h2>Category: {{ target_category }}</h2>

<ul>
  {% for post in site.categories[target_category] %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
    </li>
  {% endfor %}
</ul>





