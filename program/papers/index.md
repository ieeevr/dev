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
                {% for session in site.data.sessions %}
                    <tr>
                        <td class="medLarge"><a href="#{{ session.id }}">{{ session.session }}</a></td>
                        <td class="medLarge"><a href="#{{ session.id }}">{{ session.name }}</a></td>
                    </tr>
                {% endfor %}
            </table>
        </div>
    <div>
</div>
<div>
    {% for session in site.data.sessions %}
            <h2 id="{{ session.id }}" class="pink" style="padding-top:25px;">Session: {{ session.name }} ({{ session.session }})</h2>
            {% for paper in site.data.papers %}                 
                {% if session.session == paper.session %}         
                    <p class="medLarge" id="{{ paper.id }}" style="margin-bottom: 0.3em;">
                        <strong>{{ paper.title }}</strong>
                    </p>
                    {% for acpaper in site.data.acceptedpapers %}    
                        {% if acpaper.ids | strip == paper.id | strip %} 
                        <div>
                            Test
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
                        </div>
                        {% endif %}
                    {% endfor %}
                {% endif %}
            {% endfor %}
    {% endfor %}
</div>
