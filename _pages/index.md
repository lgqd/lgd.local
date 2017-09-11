---
title: Laboratório Gráfico Desviante
permalink: '/'
---
<img id="home-image" src="{{ site.baseurl}}/assets/covers/LGD_Freud.gif" onclick="show(0)">

<div class="text-list">
{% for page in site.pages %}
  {% if page.pdf %}
    {% for file in site.static_files %}
      {% if file.path contains page.pdf %}
        <a class="menu-item" href="{{site.baseurl}}{{ file.path }}" target="_blank">
          {{ page.title }}
        </a>
      {% endif %}
    {% endfor %}
  {% endif %}
{% endfor %}
</div>

<script>
  function show(next) {
    var imgElement = document.getElementById('home-image');
    imgElement.setAttribute('src', '{{ site.baseurl}}/assets/images/'+next+'.gif');
    imgElement.setAttribute('onclick', 'show('+(next+1)%5+')');
  }
</script>
