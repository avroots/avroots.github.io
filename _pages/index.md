---
title: home
layout: default
permalink: / # This ensures it remains the site's root page, e.g., https://avroots.nl/
---

# Alumnivereniging Roots

Alumnivereniging Roots, de vereniging voor alumni van Studievereniging A–Eskwadraad, van de Universiteit Utrecht. Wil je weer is bijpraten met je oud-studiegenoten? Kom naar een van onze laagdrempelige activiteiten!

<br/><br/>

## Volgende Activiteit
<!-- find out if there is a next_event and show it -->
{% assign upcoming_events = site.activiteiten | sort: 'eventdate' | where_exp: "event", "event.eventdate >= site.time" %}
{% if upcoming_events.size > 0 %}
{% assign next_event = upcoming_events.first %}
{% include event-details.html activiteit=next_event aslink=true %}

<!-- if the next event is tomorrow or today, also show the event afther that -->
{% if upcoming_events.size > 1 %}
{% assign next_event_date_string = next_event.eventdate | date: "%Y-%m-%d" %}
{% assign tomorrow_timestamp = site.time | date: "%s" | plus: 86400 %}
{% assign tomorrow_date_string = tomorrow_timestamp | date: "%Y-%m-%d" %}
{% if next_event_date_string <= tomorrow_date_string %}
{% assign next_next_event = upcoming_events[1] %}
{% include event-details.html activiteit=next_next_event aslink=true %}
{% endif %}

{% endif %}

<!-- if there are no upcomming events, show a short msg -->
{% else %}
Er zijn momenteel geen aankomende activiteiten gepland.<br/>
Kom binnenkort terug voor updates!
{% endif %}

<p style="text-align:right;">
<a href="/activiteiten.html">.. of bekijk alle activiteiten</a>
</p>

<br/><br/>

{% include mailchimp_form.html %}

<br/><br/>

## Word Roots lid
[Ook lid worden? vul dit formulier in!](https://forms.gle/4yzGaSdxB1vhu1eK9)

Zonder leden geen geen vereniging, en zonder vereniging geen activiteiten! Je kan A.V. Roots steunen door lid te worden en de jaarlijkse contributie van €10,- te betalen.

- Een geupdate persoonlijke digitale **lidmaatschapskaart**, met lidnummer!
- Als van te voren aangegeven, een **gratis drankje** bij een activiteit
- **Voorrang** op activiteiten waar weinig plek is
- De wetenschap dat Roots de website, bankrekening en andere dingen kan betalen dankzij **jou genereuze gift**.


<br/><br/>
<p style="text-align:right;font-size:smaller;">Site gegenereerd op: {{ site.time | date: "%d-%m-%Y %H:%M %Z" }}</p>