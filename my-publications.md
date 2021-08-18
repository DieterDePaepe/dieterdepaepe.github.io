---
---


{% for publication in site.publications reversed %}
  <section class="publication" id="{{ publication.key }}">
    <h2>{{ publication.title }}</h2>
	<span class="authors">{{ publication.authors }}</span>
	<br>
	<span class="details">
	  {% if publication.publisherartefact %}
	    {{ publication.publisherartefact }} -
	  {% endif %}
	  {{ publication.year }}
	</span>
	
	{% if publication.abstract %}
	<div class="abstract" id="abstract-{{ publication.key }}" class="collapse">
      <strong>Abstract: </strong>{{ publication.abstract }}
	</div>
	{% endif %}
	
	
	<div>
	  <pre id="bib-{{ publication.key }}" class="collapse">{{ publication.content }}</pre>
	</div>
    
	<div class="links">
	  {% if publication.fulltext %}
	    <a href="{{ publication.fulltext }}" target="_blank">Full text</a>
	  {% endif %}
	  {% if publication.abstract %}
	  <a data-toggle="collapse" href="#abstract-{{ publication.key }}" role="button" aria-expanded="false" aria-controls="collapseExample">Abstract</a>
	  {% endif %}
      <a data-toggle="collapse" href="#bib-{{ publication.key }}" role="button" aria-expanded="false" aria-controls="collapseExample">BibTex</a>
	  {% if publication.presentation %}
	    <a href="{{ publication.presentation }}" target="_blank">Presentation</a>
	  {% endif %}
	  {% if publication.preprint %}
	    <a href="/files/publications/{{ publication.preprint | escape }}" target="_blank">Preprint</a>
	  {% endif %}
	</div>
	
  </section>
{% endfor %}
