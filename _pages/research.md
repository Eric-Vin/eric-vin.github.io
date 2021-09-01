---
layout: splash
permalink: /research
---
&nbsp;

# Research

## Papers

<style>
.paper_item {
  font-size: 85%;
  margin: 1.5em 0;
  line-height: 1em;
}

.paper_title {
  margin-bottom: 0.5em;
  line-height: 1.2em;
  font-weight: bold;
}

.paper_authors,
.paper_date_loc,
.paper_type,
.paper_links {
  font-size: 75%;
  margin-bottom: 0.25em;
}

.paper_notes {
  font-size: 60%;
  margin-bottom: 0.25em;
}

</style>

{% assign papers = site.papers | sort: "year" | reverse %}
{% for pap in papers %}
<div class="paper_item">
  <div class="paper_title">{{ pap.title }}</div>
  <div class="paper_authors">{{ pap.authors }}</div>
  <div class="paper_date_loc"> 
    {% if pap.short_venue %} 
      {{ pap.short_venue}}
    {% endif %}
    {% if pap.full_venue %}
      {{pap.year}},
    {% else %}
      {{pap.year}}
    {% endif %}
    {% if pap.full_venue %}
      ({{ pap.full_venue }})
    {% endif %}
  </div>
  <div class="paper_type"> {{pap.type}} </div>
  {% if pap.notes %}
    <div class="paper_notes"> <em> Note: {{pap.notes}} </em> </div>
  {% endif %}
  <div class="paper_links">
    {% if pap.link %}
      <a href="{{pap.link}}">[PDF]</a>
    {% endif %}
    {% if pap.doi %}
      <a href="{{pap.doi}}">[DOI]</a>
    {% endif %}
  </div>
</div>
{% endfor %}

## Projects and Tools

<style>
.proj_item {
  margin: 1.5em 0;
  line-height: 1em;
}

.proj_title {
  margin-bottom: 0.5em;
  line-height: 1.2em;
  font-weight: bold;
}

.proj_description {
  font-size: 75%;
  margin-bottom: 0.25em;
}

.proj_teaser {
  position: relative;
  clear: both;
}

.proj_teaser a {
  float: left;
  margin-right: 2em;
}

.proj_teaser img {
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 200px;
}

.proj_links {
  font-size: 75%;
  margin-bottom: 0.25em;
}
</style>

{% assign projects = site.projects%}
{% for proj in projects %}
<div class="proj_item">
  <div class="proj_teaser">
    <a href="{{proj.link}}">
      <img
        src="/images/projects/{{proj.icon}}"
        class="thumbnail"
      >
    </a>
  </div>
  <div class="proj_title">{{proj.title}}</div>
  <div class="proj_description">{{proj.description}}</div>
  <div class="proj_links">
    {% if proj.github %}
      <a href="{{proj.github}}">[GitHub]</a>
    {% endif %}
    {% if proj.pypi %}
      <a href="{{proj.pypi}}">[PyPi]</a>
    {% endif %}
  </div>
</div>
{% endfor %}
