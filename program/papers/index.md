---
layout: ieeevr-default
title: "Papers"
subtitle: "IEEE VR 2024"
title_separator: "|"
---
<h1>Papers</h1>
<div>
    <div>
        <div>
            <table class="styled-table">
                <tr>
                    <th colspan="4">{{ day.day }} (Timezone: {{ day.timezone }})</th>
                </tr>
                {% for session in site.data.sessions %}
                    <tr>
                        <td class="medLarge"><a href="#{{ session.id }}">{{ session.id }}</a></td>
                        <td class="medLarge"><a href="#{{ session.id }}">{{ session.name }}</a></td>
                        <!--<td class="medLarge">{{ session.starttime }}&#8209;{{ session.endtime }}</td>
                        <td class="medLarge" class="text-nowrap">{{ session.room }}</td>-->
                    </tr>
                {% endfor %}
            </table>
        </div>
    <div>
    <!--{% for day in site.data.days %}
        <div>
            <div>
                <table class="styled-table">
                    <tr>
                        <th colspan="4">{{ day.day }} (Timezone: {{ day.timezone }})</th>
                    </tr>
                    {% for session in site.data.sessions %}
                        {% if session.day == day.day %}
                            <tr>
                                <td class="medLarge"><a href="#{{ session.id }}">{{ session.id }}</a></td>
                                <td class="medLarge"><a href="#{{ session.id }}">{{ session.name }}</a></td>
                                <td class="medLarge">{{ session.starttime }}&#8209;{{ session.endtime }}</td>
                                <td class="medLarge" class="text-nowrap">{{ session.room }}</td>
                            </tr>
                        {% endif %}
                    {% endfor %}
                </table>
            </div>
        <div>
    {% endfor %} -->
</div>
<div>
    {% for session in site.data.sessions %}
            <h2 id="{{ session.id }}" class="pink" style="padding-top:25px;">Session: {{ session.name }} ({{ session.id }})</h2>
            {% for paper in site.data.papers %}                 
                {% if session.Session == paper.session %}         
                    <p class="medLarge" id="{{ paper.id }}" style="margin-bottom: 0.3em;">
                        <strong>{{ paper.title }} ({{ paper.type }}: {{ paper.id }})</strong>
                    </p>
                    <p class="font_70" >
                        {% assign authornames = p.authors | split: ";" %}
                        {% for name in authornames %}
                            {% assign barename = name | split: ":" %}
                            {% for n in barename %}
                                {% if n == barename.last %}
                                    <i>{{ n | strip }}{% if name == authornames.last %}{% else %};{% endif %}</i>
                                {% else %}                            
                                    <span class="bold">{{ n | strip }},</span>
                                {% endif %}
                            {% endfor %} 
                        {% endfor %}
                    </p>
                    {% if p.abstract %}
                        <div id="{{ paper.id }}" class="wrap-collabsible"> <input id="collapsible{{ paper.id }}" class="toggle" type="checkbox"> 
                            <label for="collapsible{{ paper.id }}" class="lbl-toggle">Abstract</label>
                            <div class="collapsible-content">
                                <div class="content-inner">
                                    <p>{{ p.abstract }}</p>
                                </div>
                            </div>
                        </div>                                                                     
                    {% endif %}
                {% endif %}
            {% endfor %}
    {% endfor %}
</div>
