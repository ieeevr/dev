---
layout: ieeevr-default
title: "Posters"
subtitle: "IEEE VR 2024"
title_separator: "|"
---

<h1>Posters</h1>
<div>
    <table class="styled-table">
        <tr>
            <th colspan="3">Posters (Timezone: Saint-Malo, France UTC+1)</th>
        </tr>
        <tr>
            <td class="medLarge"><a href="#P1"></a></td>
            <h1 id="call-for-workshop-papers"> Monday Posters </h1>
                {% for cat in site.data.postersCategories %}
                Category : {{ cat.name }}
                <div>                    
                    <tr>
                        <th colspan="4">Category: {{ cat.id }}  {{ cat.name }} (Day : {{ cat.day}})</th>
                    </tr>                   
                    {% assign ps = site.data.posters | sort: "id" %}
                    {% for poster in ps %}
                        {% if poster.PosterCategory == cat.id and poster.Day == cat.day %}
                            <tr>
                                <td class="medLarge"><a href="#{{ ps.id }}">{{ ps.id }}</a></td>
                                <td class="medLarge"><a href="#{{ ps.id }}">{{ ps.title }}</a></td>
                            </tr>
                        {% endif %}
                    {% endfor %}
                <div>
            {% endfor %} 
            <td class="medLarge"><a href="#P1"></a></td>
            <h1 id="call-for-workshop-papers"> Monday Posters </h1>
                {% for cat in site.data.postersCategories2 %}
                Category : {{ cat.name }}
                <div>
                    <div>
                        <table class="styled-table">
                            <tr>
                                <th colspan="4">Category: {{ cat.id }}  {{ cat.name }} (Day : {{ cat.day}})</th>
                            </tr>                   
                            {% assign ps = site.data.posters | sort: "id" %}
                            {% for poster in ps %}
                                {% if poster.PosterCategory == cat.id and poster.Day == cat.day %}
                                    <tr>
                                        <td class="medLarge"><a href="#{{ ps.id }}">{{ ps.id }}</a></td>
                                        <td class="medLarge"><a href="#{{ ps.id }}">{{ ps.title }}</a></td>
                                    </tr>
                                {% endif %}
                            {% endfor %}
                        </table>
                    </div>
                <div>
            {% endfor %} 
        </tr>
    </table>
</div>

<div>    
    <h2 id="P1" class="pink" style="padding-top:25px;">Monday Posters</h2>  
    <p class="small">Talk with the authors: 9:45&#8209;10:15, 13:00&#8209;13:30, 15:00&#8209;15:30, 17:00&#8209;17:30, Room: Sorcerer's Apprentice Ballroom</p>  
    {% for poster in site.data.posters %}
        <div style="margin-left: 25px;">           
            <p class="medLarge" id="{{ poster.id }}" style="margin-bottom: 0.3em;">
                <strong>{{ poster.title }} (ID:&nbsp;{{ poster.id }})</strong>
            </p>
            <p class="font_70" >
                {% assign authornames = poster.Authors | split: ";" %}
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
            {% if poster.Abstract %}
                <div id="{{ poster.id }}" class="wrap-collabsible"> <input id="collapsibleabstract{{ poster.id }}" class="toggle" type="checkbox"> 
                    <label for="collapsibleabstract{{ poster.id }}" class="lbl-toggle">Abstract</label>
                    <div class="collapsible-content">
                        <div class="content-inner">
                            <p>{{ poster.Abstract }}</p>
                        </div>
                    </div>
                </div>   
            {% endif %}
            {% if poster.VideoLink %}
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/{{ poster.VideoLink }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
        {% endif %}
        </div>
    {% endfor %}
</div>
