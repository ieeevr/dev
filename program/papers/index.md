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
                    <th colspan="4">Paper presentations sessions</th>
                </tr>    
                {% for session in site.data.sessions %}
                    <tr>
                        <td class="medLarge"><a href="#{{ session.id }}">{{ session.session }} - {{ session.room }}</a></td>
                        <td class="medLarge"><a href="#{{ session.id }}">{{ session.name }}</a></td>
                        {% for room in site.data.rooms %} 
                            {% if room.session == session.session %}
                                {% if room.room == session.room %}
                                    <td class="medLarge">{{ room.starttime }}&#8209;{{ room.endtime }}</td>
                                    <td class="medLarge" class="text-nowrap">{{ room.room }}</td>
                                {% endif %}
                            {% endif %}
                        {% endfor %}
                    </tr>
                {% endfor %}
            </table>
        </div>
    <div>
</div>
<div>
    {% for session in site.data.sessions %}
            <h2 id="{{ session.id }}" class="pink" style="padding-top:25px;">Session: {{ session.name }} ({{ session.session }} - {{ session.room }})</h2>
            {% for paper in site.data.papers %}                 
                {% if session.session == paper.session %}
                    {% if paper.room == session.room %}         
                        <p class="medLarge" id="{{ paper.id }}" style="margin-bottom: 0.3em;">
                            <strong>{{ paper.title }}</strong>
                        </p>
                        <p class="font_70">
                        {% for acpaper in site.data.acceptedpapers %}    
                            {{ acpaper.ids }} | {{ paper.id }}
                            {% if acpaper.ids == paper.id  %} 
                                {% assign authornames = acpaper.affiliations | split: "," %}
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
                            {% endif %}
                        {% endfor %}
                        </p>
                    {% endif %}
                {% endif %}
            {% endfor %}
    {% endfor %}
</div>
