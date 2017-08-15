---
title: Laboratório Gráfico Desviante
permalink: '/'
---
<img id="home-image" class="home-click" src="{{ site.baseurl}}assets/covers/LGD_Freud.gif" onclick="show('text')">

<div id="home-text" class="home-click" markdown="1" style="display: none;" onclick="show('image')">
  **vandalism**  
  van.dal.ism (noun) **1** Action involving deliberate destruction of or damage to public or private property. **2** Willful or ignorant destruction of artistic or literary treasures.
</div>


<div class="menu-item menu-title">Textos</div>
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
  function show(thing) {
    var notThing = (thing == 'text')?'image':'text';

    document.getElementById('home-'+thing).style.display = 'block';
    document.getElementById('home-'+notThing).style.display = 'none';
  }
</script>
