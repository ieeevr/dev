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
                        <td><a href="#{{ cat.id }}">{{ cat.name }} - {{cat.infos}}</a></td>
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
                {% if poster.day == cat.day %}
                    {% if poster.cat== cat.id %}
                    <div >       
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
                            <div id="{{ poster.id }}" class="wrap-collabsible"> <input id="collapsibleabstract{{ poster.id }}" class="toggle" type="checkbox"> 
                                <label for="collapsibleabstract{{ poster.id }}" class="lbl-toggle">Abstract</label>
                                <div class="collapsible-content">
                                    <div class="content-inner">
                                        <p>{{ poster.abstract }}</p>
                                    </div>
                                </div>
                            </div>   
                        {% endif %}
                        {% if poster.url %}
                        <div class="video-container">
                            <iframe src="https://www.youtube.com/embed/{{ poster.url }}" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                        </div>
                        {% endif %}
                    </div>
                    {% endif %}
                {% endif %}
            {% endfor %}
        {% endfor %}
    </div>
    {% endfor %}
</div>
