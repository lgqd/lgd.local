---
title: Laboratório Gráfico Desviante
permalink: '/'
---
<img id="home-image" class="home-click" src="{{ site.baseurl}}/assets/covers/LGD_Freud.gif" onclick="show('text')">

<div id="home-text" class="home-click" markdown="1" style="display: none;" onclick="show('image')">
  **Laboratório Gráfico Desviante (LGD)**  
  é um grupo composto por diferentes profissionais que combinam artes visuais, escrita, dança, design gráfico e programação, cujas pesquisas envolvem o questionamento dessas linguagens a partir de suas normatizações e cânones. O objetivo do LGD não é negar as estruturas problematizadas com a intenção de gerar novos cânones, mas discutir e compreender os sistemas de cada linguagem e os possíveis níveis de desconstruções, infiltrações e hackeamentos.
</div>


{% comment %}
<div class="menu-item menu-title">Textos</div>
{% endcomment %}

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
