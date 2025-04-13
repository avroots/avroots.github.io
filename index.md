---
layout: home
title: Alumni Vereniging Roots
---

# Welkom bij A.V. Roots

Welkom op de officiële website van Alumni Vereniging Roots! Wij zijn een actieve vereniging van afgestudeerden die de band met elkaar en onze alma mater levend houden door regelmatig bijeenkomsten en activiteiten te organiseren.

## Aankomende Activiteit

{% assign upcoming_events = site.categories.activiteiten | sort: 'date' | where_exp: "event", "event.date >= site.time" %}
{% if upcoming_events.size > 0 %}
{% assign next_event = upcoming_events.first %}

<div class="featured-event">
  <h3><a href="{{ next_event.url }}">{{ next_event.title }}</a></h3>
  <p class="event-date">{{ next_event.date | date: "%d-%m-%Y" }} om {{ next_event.time }}</p>
  <p class="event-location">Locatie: {{ next_event.location }}</p>
  <p class="event-cost">Kosten: {{ next_event.cost }}</p>
  <a href="{{ next_event.url }}" class="button">Meer informatie</a>
</div>
{% else %}
<p>Er zijn momenteel geen aankomende activiteiten gepland. Kom binnenkort terug voor updates!</p>
{% endif %}

## Over A.V. Roots

A.V. Roots verbindt alumni met elkaar en met de actuele ontwikkelingen in het vakgebied. Door lid te worden krijg je toegang tot ons netwerk van professionals, interessante lezingen, workshops en sociale evenementen.

## Word Lid

Ben je alumnus en wil je deel uitmaken van ons netwerk? Word dan lid van A.V. Roots! Als lid krijg je toegang tot alle evenementen, ontvang je onze nieuwsbrief en kun je gebruik maken van speciale kortingen.

[Meer informatie over lidmaatschap](/lidmaatschap)

## Contact

Voor vragen of meer informatie kun je ons bereiken via [bestuur@avroots.nl](mailto:bestuur@avroots.nl).