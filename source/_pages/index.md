---
layout: default
title: Shenomenal
permalink: /
---

<!-- intro -->
<div class="masonry-wrapper">
  <div class="container align-center">
    <h1 class="title"><strong>She</strong>nomenal</h1>
    <p class="three-fourth">This International Women's Day, we are lifting up the achievements of 35 phenomenal UC Santa Cruz women. From astronomers and astronauts to activists, journalists, judges, and so much more, these women are trailblazers, and many have been "firsts" in their fields. For us, these women exemplify the words immortalized by the poet Maya Angelou: "I’m a woman / Phenomenally. / Phenomenal woman, / That’s me."</p>
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
          Share: <a href="https://twitter.com/intent/tweet?text={{ list.first }}{{ list.last }}: {{ list.bio | truncate: 100 }}&amp;url={{ site.url }}%23{{ list.last | downcase | replace: ' ', ''}}" class="social"><i class="fab fa-twitter"></i></a>  <a href="https://www.facebook.com/sharer/sharer.php?t={{ list.first }}{{ list.last }}: {{ list.bio | truncate: 100 }} &u={{ site.url }}/%23{{ list.last | downcase | replace: ' ', ''}}?ref=share" class="social"><i class="fab fa-facebook-f"></i></a>  <a href="http://www.linkedin.com/shareArticle?mini=true&amp;title={{ list.first }}{{ list.last }} &amp;url={{ site.url }}/%23{{ list.last | downcase | replace: ' ', ''}}" class="social"><i class="fab fa-linkedin"></i></a>
        </div>
      </div>
    {% endfor %}
  </div>
  <!-- end mansonry container -->
</div>
<!-- end mansonry-wrapper -->

