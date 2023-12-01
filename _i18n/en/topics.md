<div id="title-banner" class="written">
  <h1>{% t page.title %}</h1>
  <hr>  
</div>

{% for ext in site.data.category %}
  <section>
    <h2 id="{{ ext }}">.{{ ext }} | {% t topics.{{ ext }} %}</h2>
    <ul>
    {% for post in site.posts %}
      {% if post.keywords contains ext %}
        <li>
          {{ post.date | date: "%b %-d, %Y" }}
          <a href="{{ post.url | prepend:site.baseurl }}">
            {{ post.title }}
          </a>
        </li>
      {% endif %}
    {% endfor %}
    </ul>
  </section>
{% endfor %}
