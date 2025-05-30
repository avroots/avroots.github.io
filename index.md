---
title: Home
layout: default
---

# Alumni Vereniging Roots

Wij zijn Alumni Vereniging Roots, de vereniging voor alumni van Studievereniging A–Eskwadraad, van de Universiteit Utrecht. Wil je weer is bijpraten met je oud-studiegenoten? Kom naar een van onze laagdrempelige activiteiten!

<br/><br/>

## Volgende Activiteit
{% assign upcoming_events = site.activiteiten | sort: 'eventdate' | where_exp: "event", "event.eventdate >= site.time" %}
{% if upcoming_events.size > 0 %}
{% assign next_event = upcoming_events.first %}
{% include event-details.html activiteit=next_event showlink=true %}
{% else %}
Er zijn momenteel geen aankomende activiteiten gepland.<br/>
Kom binnenkort terug voor updates!
{% endif %}

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
