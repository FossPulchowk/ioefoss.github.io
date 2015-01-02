---
layout: page
type: page
title: Projects
permalink: /Projects/
---
This page will contains list of all open source projects done by Pulchowk Students and present in FossPulchowk github organization.

<table>
  <h2>My Projects</h2>
  
    {% for pages in site.pages %}
    {% if pages.type == "project-subpage" %}
  <tr>
    <td>
      <a href="{{ pages.url }}">
	{% if pages.title %}
	{{ pages.title}}
	{% else %}
	{{ pages.url }}
	{% endif %}
      </a>
    </td>
  </tr>
  <tr>
    <td>
    {{ pages.excerp }}
    </td>
  </tr>
  {% endif %}
    {% endfor %}
</table>
