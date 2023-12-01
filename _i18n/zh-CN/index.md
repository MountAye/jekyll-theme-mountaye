<style>
  #home {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
  }
  #home a {
    margin: 1rem 0;
    width: fit-content;
    display: block;
    color: black;
    text-decoration: none;
    border-bottom: transparent;
  }
</style>
<div id="home" class="written">
  {% assign post = site.posts[0] %}
  <a href="{{ post.url | prepend:site.baseurl }}"
     style="display:block; text-decoration:none; color:inherit; margin-top:50px"
  >
    <h2 id="{{post.title}}">{{ post.title }}</h2>
    <span>
      {{ post.date | date: "%Y年%-m月%-d日" }} | {% for key in post.keywords %}.{{ key }} {% endfor %}
    </span>
    <p>{{ post.excerpt | strip_html | truncatewords: 80 }}</p>
  </a>

  {% for i in (1..4) %}
    {% assign post = site.posts[i] %}
    <hr>
    <a href="{{ post.url | prepend:site.baseurl }}">
      <span>{{ post.date | date: "%Y年%-m月%-d日" }} | </span>
      <h3 id="{{ post.title }}">{{ post.title }}</h3>
      {% for key in post.keywords %}<code class="language-plaintext highlighter-rouge">.{{ key }}</code> {% endfor %}
    </a>
  {% endfor %}
</div>