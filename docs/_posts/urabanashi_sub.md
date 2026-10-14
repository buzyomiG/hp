
{% assign target_category = "裏話" %}

法人化の裏話については、別ページにまとめています。

こちらのページはそれ以外の裏話をまとめています。

<h2>Category: {{ target_category }}</h2>

<ul>
  {% for post in site.categories[target_category] %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
    </li>
  {% endfor %}
</ul>





