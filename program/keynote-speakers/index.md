---
layout: ieeevr-default
title: "Keynote Speakers"
subtitle: "IEEE VR 2025"
title_separator: "|"
---

<h1>Keynote Speakers</h1>
<div>
    <table class="styled-table">
        <tr>
            <th colspan="3">Speakers</th>
        </tr>
        {% for keynote in site.data.keynotes %}
        <tr>
            <td><a href="#{{ keynote.id }}"><img src="{{ keynote.thumbnail }}" alt="Photo of {{ keynote.name }}"></a></td>
            <td><a href="#{{ keynote.id }}">{{ keynote.name }}</a></td>
            <td style="font-size: 0.875em;">{{ keynote.day }}, {{ keynote.start }} - {{ keynote.end }} ({{ keynote.timezone }})<br>Room: {{ keynote.room }}</td>
        </tr>
        {% endfor %}
    </table>
</div>
{% for keynote in site.data.keynotes %}
<br />
<div id="{{ keynote.id }}">
    <center><strong><big>{{ keynote.name }}</big></strong></center>
    <center>{{ keynote.affiliation }}</center>
    <br />
    <center><img src="{{ keynote.photo }}" alt="Photo of {{ keynote.name }}" width="50%"></center>
    <br />
    <center><big><strong>{{ keynote.title }}</strong></big></center>
    <center><small>{{ keynote.day }}, {{ keynote.start }} - {{ keynote.end }} ({{ keynote.timezone }})<br>Room: {{ keynote.room }}</small></center>
    {% if keynote.chair %}
    <center><small>Session Chair: <b style="font-family: 'Courier New', monospace; color: black;">{{ keynote.chair }}</b></small></center>
    {% endif %}    
    <p>
        <strong>Abstract</strong><br />
        {{ keynote.abstract }}
    </p>
    <p>
        <strong>Bio</strong><br />
        {{ keynote.bio }}
    </p>
    <hr>
</div>
{% endfor %}

