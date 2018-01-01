---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
title: 'Magento Meetup Austria - nächster Termin: 01.02.2018 in Wien!'
---
<section id="main_content" class="inner">

<div class="feature_container">
    <div class="feature">
        <p>Hallo und herzlich willkommen! Dieses Meetup ist eine Veranstaltung von der Community für die Community. Wir treffen uns seit 2012 und diskutieren über Magento und E-Commerce.</p>
        <h1>Nächste Veranstaltung</h1>
        {% assign future_meetups = site.meetups | where: 'done', 'no' | sort: 'meetup_number' %}
        {% if future_meetups.size == 0 %}
        <p>Der Termin für das nächste Meetup steht noch nicht fest.</p>
        {% else %}
        {% for meetup in future_meetups %}
        <h3><a href="{{ meetup.url }}">{{ meetup.meetup_number | escape }}. Magento-Meetup am {{ meetup.meetup_date | date: "%d.%m.%Y" }}{% if meetup.meetup_city %} in {{ meetup.meetup_city | escape}}{% endif %}{% if meetup.subtitle %}: {{ meetup.subtitle | esacpe }}{% endif %}</a></h3>
        <p>Hallo und herzlich willkommen! Dieses Meetup ist eine Veranstaltung von der Community für die Community. Wir treffen uns seit 2012 und diskutieren über Magento und E-Commerce.</p>
        {{ meetup.content }}
        
        <h3>Agenda</h3>
        
        <ul>
            {% if meetup.agenda.size > 0 %}
            {% for item in meetup.agenda %}
            <li>{{ item }}</li>
            {% endfor %}
            {% else %}
            <li><strong>TBA</strong></li>
            {% endif %}
        </ul>

        <h3>SpeakerInnen gesucht</h3>
        <p>Wir würden uns sehr freuen, Sie bei uns als SpeakerIn begrüßen zu dürfen! Es kann, muss sich aber nicht um ein Magento-Thema handeln.</p>

        <h3>Anmeldung</h3>
        {% if meetup.registrations.size > 0 %}
            {% for registration_hash in meetup.registrations %}
              {% for link in registration_hash %}
                {% case link[0] %}
                 {% when 'meetup' %}
                   {% assign button_label = 'meetup.com' %}
                 {% when 'xing' %}
                   {% assign button_label = 'XING' %}
                 {% else %}
                   {% assign button_label = link[0] %}
                {% endcase %}
                 <p><a href="{{ link[1] }}" target="_new" class="call-to-action">Anmeldung via {{ button_label }}</a></p>
              {% endfor %}
            {% endfor %}
        {% else %}
            <p>Die Anmeldung wird demnächst freigeschaltet.</p>
        {% endif %}
        {% endfor %}
        {% endif %}
    </div>
</div>
<p class="left"><a href="https://www.xing.com/communities/groups/magento-oesterreich-usergruppe-712b-1064068" class="call-to-action">Meetup bei XING</a></p>
<p class="right"><a href="https://www.meetup.com/magento-meetup-austria/" class="call-to-action">Meetup auf meetup.com</a></p>
<p class="left"><a href="http://facebook.com/pg/MageAT/" class="call-to-action">Meetup bei Facebook</a></p>
<p class="right"><a href="https://www.slideshare.net/magentomeetupaustria/" class="call-to-action">Meetup bei Slideshare</a></p>
<h2 class="clear">Das Meetup auf Twitter: <a href="https://twitter.com/mage_AT">@mage_AT</a></h2>
  <p>Unser offizieller Account ist <a href="https://www.twitter.com/mage_AT">@mage_AT</a>. Bitte helfen Sie uns mit Mentions über @mage_AT oder #mageAT, neue BesucherInnen zu finden!</p>
  <a class="twitter-timeline"  href="https://twitter.com/hashtag/mageAT" data-widget-id="866591655037730816">#mageAT-Tweets</a>
  <script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+"://platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");</script>

          
<h2>Vergangene Veranstaltungen</h2>
{% assign past_meetups = site.meetups | where: 'done', 'yes' | sort: 'meetup_number' | reverse %}

<ul>
{% for meetup in past_meetups %}
  <li><a href="{{ meetup.url }}">{{ meetup.meetup_number | escape }}. Magento-Meetup am {{ meetup.meetup_date | date: "%d.%m.%Y" }}{% if meetup.meetup_city %} in {{ meetup.meetup_city | escape}}{% endif %}{% if meetup.subtitle %}: {{ meetup.subtitle | esacpe }}{% endif %}</a></li>
{% endfor %}
</ul>

</section>
