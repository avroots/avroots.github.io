---
title: Activiteiten
layout: default
---

# Activiteiten
{% assign upcoming_activities = site.activiteiten | where_exp: "activity", "activity.eventdate >= site.time" | sort: 'eventdate' %}
{% if upcoming_activities.size > 0 %}
{% for activity in upcoming_activities %}

{% include event-details.html activiteit=activity showlink=true %}

{% endfor %}
{% else %}
Er zijn momenteel geen aankomende activiteiten gepland.
{% endif %}


<br><br>
### oude activiteiten
{% assign past_activities = site.activiteiten | where_exp: "activity", "activity.eventdate < site.time" | sort: 'eventdate' | reverse %}
{% if past_activities.size > 0 %}
  {% assign activities_by_year = past_activities | group_by_exp: "activity", "activity.eventdate | date: '%Y'" %}
  {% for year_group in activities_by_year %}
  <br/><br/>
<h2>{{ year_group.name }}</h2>
    {% for activity in year_group.items %}

{% include event-details.html activiteit=activity showlink=true %}

    {% endfor %}
  {% endfor %}
{% else %}
Er zijn nog geen vorige activiteiten om weer te geven.
{% endif %}