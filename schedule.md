---
layout: default
title: Zeitplan
---

# Zeitplan
----------

<table class="table table-striped"> 
  <tbody>
    <tr>
      <th>Datum</th>
      <th>Thema</th>
      <th width="20%">Übungen</th>
    </tr>
	
    {% for lecture in site.data.schedule.lectures %}
    <tr>
        <td>{{ lecture.date | date: "%d %b" }}</td>
        <td>
		   <p class="{{ lecture.type }}">		  
            {% if lecture.slides %}
				<a href="{{ lecture.slides }}">{{ lecture.title }}</a>
            {% else %}
				{{ lecture.title }}
			{% endif %}
			
            {% if lecture.links %}
				{% for link in lecture.links %}
	                <br/>- <a href="{{ link.url }}">{{ link.text }}</a>
                {% endfor %}
            {% endif %}
		    </p>
        </td>
		
       

	  <td>
	    {% if lecture.assignment %}
		  {% if lecture.assignment_url %}
		    <a href="{{ lecture.assignment_url }}">{{ lecture.assignment }}</a>
	      {% else %}
            {{ lecture.assignment }}
		  {% endif %}
	    {% endif %}
	  </td>
    </tr>
    {% endfor %}
  </tbody>
</table>
