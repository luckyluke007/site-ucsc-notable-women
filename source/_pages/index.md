---
layout: default
title: Home
permalink: /
---

<!-- intro -->
<div class="masonry-wrapper">
  <div class="container align-center">
    <h1 class="title"><strong>She</strong>nomenal</h1>
    <p class="three-fourth">UC Santa Cruz phenomenal women... Nunc egestas congue mollis. Ut nec purus a mi cursus placerat eget ac neque. Integer laoreet purus id gravida maximus. Nullam in velit eget mi faucibus facilisis sit amet quis urna. Sed vel tristique arcu. Curabitur facilisis justo sed enim condimentum, eu vestibulum tellus lobortis.</p>
    <form>
      <select id="nav" name="nav">
        <option value="">Select a Banana Slug</option>
        {% for list in site.data.lists %}
        <option value="{{ list.last | downcase | replace: ' ', '' }}">{{ list.first }} {{ list.last }}</option>
        {% endfor %}
      </select>
    </form>
  </div>
  <!-- mansonry container -->
  <div class="masonry">
    {% assign lists = site.data.lists | sort_natural: 'first' %}
    {% for list in lists %}
      <div class="masonry-item {% if list.featured != null %} featured {% endif%}" id="{{ list.last | downcase | replace: ' ', '' }}">
        {% if list.photo != null %}
          <img src="{{ list.photo }}" alt="{{ list.first }}{{ list.last }}">
        {% endif %}
        <h2>{{ list.first }} {{ list.last }}</h2>
        <p class="affiliation">{{ list.title }}</p>
        <p>{{ list.bio }}</p>
        <div class="share-content">
          Share: <a href="https://twitter.com/intent/tweet?text={{ list.first }}{{ list.last }}: {{ list.bio | truncate: 100 }}&amp;url={{ site.url }}%23{{ list.last | downcase | replace: ' ', ''}}" class="social"><i class="fab fa-twitter"></i></a>  <a href="https://www.facebook.com/sharer/sharer.php?t={{ list.first }}{{ list.last }}: {{ list.bio | truncate: 100 }} &u={{ site.url }}%23{{ list.last | downcase | replace: ' ', ''}}?ref=share" class="social"><i class="fab fa-facebook-f"></i></a>  <a href="http://www.linkedin.com/shareArticle?mini=true&amp;title={{ list.first }}{{ list.last }} &amp;url={{ site.url }}%23{{ list.last | downcase | replace: ' ', ''}}" class="social"><i class="fab fa-linkedin"></i></a>
        </div>
      </div>
    {% endfor %}
  </div>
  <!-- end mansonry container -->
</div>
<!-- end mansonry-wrapper -->

