---
layout: ieeevr-default
title: "Posters"
subtitle: "IEEE VR 2025"
title_separator: "|"
---


<h1>Posters</h1>
<div>
    <table class="styled-table">
        <tr>
            {% for day in site.data.postersDays %}
                <tr>
                    <th colspan="4"><a href="#{{ day.id }}">{{ day.day}} posters</a></th>
                </tr>
                {% assign category_file = day.name %}
                {% for cat in site.data[category_file] %}
                    <tr>
                        <td><a href="#{{ cat.id }}">{{ cat.name }}</a></td>
                    </tr>
                {% endfor %}
            {% endfor %}    
        </tr>
    </table>
</div>
<div>    
    {% for day in site.data.postersDays %}
    <div>
        <h1 id="{{ day.id }}" class="pink" style="padding-top:25px;">{{ day.day}} posters</h1>  
        {% assign category_file = day.name %}
        {% for cat in site.data[category_file] %}
            <h2 id="{{ cat.id }}" class="pink" style="padding-top:25px;">{{ cat.name }} </h2>  
            {% for poster in site.data.posters %}
                {% if poster.PosterCategory == cat.name %}
                    <div style="margin-left: 25px;">                                  
                        <p class="medLarge" id="{{ paper.id }}" style="margin-bottom: 0.3em;">
                            <strong>{{ poster.title }}</strong>
                        </p>
                        <p class="font_70" >
                            {% assign authornames = poster.authors | split: ";" %}
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
                        {% if poster.abstract %}
                            <div id="{{ poster.num }}" class="wrap-collabsible"> <input id="collapsibleabstract{{ poster.num }}" class="toggle" type="checkbox"> 
                                <label for="collapsibleabstract{{ poster.num }}" class="lbl-toggle">Abstract</label>
                                <div class="collapsible-content">
                                    <div class="content-inner">
                                        <p>{{ poster.abstract }}</p>
                                    </div>
                                </div>
                            </div>   
                        {% endif %}
                        {% if poster.VideoLink %}
                        <div id="{{ poster.VideoLink }}" class="wrap-collabsible"> <input id="collapsibleabstract{{ poster.VideoLink }}" class="toggle" type="checkbox"> 
                            <label for="collapsibleabstract{{ poster.VideoLink }}" class="lbl-toggle">Video</label>
                            <div class="collapsible-content">
                                <div class="content-inner">
                                    <div class="video-container">
                                        <iframe src="https://www.youtube.com/embed/{{ poster.VideoLink }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                                    </div>
                                </div>
                            </div>
                        </div>                           
                        {% endif %}
                    </div>
                {% endif %}
            {% endfor %}
        {% endfor %}
    </div>
    {% endfor %}
</div>
