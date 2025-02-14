---
layout: ieeevr-default
title: "Research Demos"
subtitle: "IEEE VR 2024"
title_separator: "|"
---

<!--<div>
    <table class="styled-table">
        <tr>
            <th colspan="2">Research Demos</th>
        </tr>        
        {% assign i = 0 %}
        {% for demo in site.data.demos %}
            {% assign i = i | plus:1 %}
            <tr>
                <td>
                    {% for a in site.data.awards %}  
                        {% if a.type == 'Demo' %}
                            {% if a.id == demo.id %}
                                {% if a.award == 'Best Demo' %}
                                    <a href="{{ "/awards/conference-awards" | relative_url }}#demo-best"><img src= "{{ "/assets/images/awards/best.png" | relative_url }}" title="Best Research Demo Award" alt="Best Research Demo Award"></a>
                                {% endif %}                                                    
                                {% if a.award == "Honorable Mention" %}
                                    <a href="{{ "/awards/conference-awards" | relative_url }}#demo-honorable"><img src= "{{ "/assets/images/awards/hm.png" | relative_url }}" title="Best Research Demo Honorable Mention" alt="Best Research Demo Honorable Mention"></a>
                                {% endif %}
                            {% endif %}
                        {% endif %}
                    {% endfor %}
                </td>
                <td class="medLarge"><a href="#{{ demo.id }}">{{ demo.title }} (ID:&nbsp;{{ demo.id }})</a></td>
            </tr>
        {% endfor %}
    </table>
</div>-->
<p>
    <table class="program-table">
        <thead>
            <tr>
                <th colspan="4">Research&nbsp;Demos&nbsp;Schedule (Timezone: Saint-Malo, France UTC+1)</th>
            </tr>
        </thead>
        <tbody> 
            {% for demodays in site.data.scheduleDemo %}
             <tr>
                <td> {{ demodays.name }}</td>
                <td> {{ demodays.day }}</td>
                <td> {{ demodays.sessions }}</td>
                <td> Hall: {{ demodays.hall }}</td>
            </tr>     
            {% endfor %}       
        </tbody>
    </table>
</p>
<h2>Research Demos</h2>
<div>
    {% assign j = 0 %}
    {% for demo in site.data.demos %}
        {% assign j = j | plus:1 %}
        <!--{% for a in site.data.awards %}  
            {% if a.type == 'Demo' %}
                {% if a.id == demo.id %}
                    {% if a.award == 'Best Demo' %}
                        <div class="align-left"><a href="{{ "/awards/conference-awards" | relative_url }}#demo-best"><img src= "{{ "/assets/images/awards/best.png" | relative_url }}" title="Best Research Demo Award" alt="Best Research Demo Award"></a></div>
                    {% endif %}                                                    
                    {% if a.award == "Honorable Mention" %}
                        <div class="align-left"><a href="{{ "/awards/conference-awards" | relative_url }}#demo-honorable"><img src= "{{ "/assets/images/awards/hm.png" | relative_url }}" title="Best Research Demo Honorable Mention" alt="Best Research Demo Honorable Mention"></a></div>
                    {% endif %}
                {% endif %}
            {% endif %}
        {% endfor %}-->
        <p class="medLarge" id="{{ demo.id }}" style="margin-bottom: 0.3em;">
            <strong>{{ demo.title }} (ID:&nbsp;{{ demo.id }})</strong>
        </p>
        Hall: {{ demo.hall}}, Booth ID : {{demo.booth}}
        <p class="font_70" >                
            {% if demo.author1first %}                         
                <span class="bold">{{ demo.author1last demo.author1first }},</span> <i> {{ demo.author1institution1}}</i>
            {% endif %}                
            {% if demo.author2first %}                         
                <span class="bold">;{{ demo.author2last demo.author2first }},</span> <i> {{ demo.author2institution1}}</i>
            {% endif %}           
            {% if demo.author3first %}                         
                <span class="bold">;{{ demo.author3last demo.author3first }},</span> <i> {{ demo.author3institution1}}</i>
            {% endif %}           
            {% if demo.author4first %}                         
                <span class="bold">;{{ demo.author4last demo.author4first }},</span> <i> {{ demo.author4institution1}}</i>
            {% endif %}           
            {% if demo.author5first %}                         
                <span class="bold">;{{ demo.author5last demo.author5first }},</span> <i> {{ demo.author5institution1}}</i>
            {% endif %}           
            {% if demo.author6first %}                         
                <span class="bold">;{{ demo.author6last demo.author6first }},</span> <i> {{ demo.author6institution1}}</i>
            {% endif %}           
            {% if demo.author7first %}                         
                <span class="bold">;{{ demo.author7last demo.author7first }},</span> <i> {{ demo.author7institution1}}</i>
            {% endif %}           
            {% if demo.author8first %}                         
                <span class="bold">;{{ demo.author8last demo.author8first }},</span> <i> {{ demo.author8institution1}}</i>
            {% endif %}           
            {% if demo.author9first %}                         
                <span class="bold">;{{ demo.author9last demo.author9first }},</span> <i> {{ demo.author9institution1}}</i>
            {% endif %}           
            {% if demo.author10first %}                         
                <span class="bold">;{{ demo.author10last demo.author10first }},</span> <i> {{ demo.author10institution1}}</i>
            {% endif %}           
            {% if demo.author11first %}                         
                <span class="bold">;{{ demo.author11last demo.author11first }},</span> <i> {{ demo.author11institution1}}</i>
            {% endif %}        
            {% if demo.author12first %}                         
                <span class="bold">;{{ demo.author12last demo.author12first }},</span> <i> {{ demo.author12institution1}}</i>
            {% endif %}  
        </p>
        {% if demo.abstract %}
            <div id="{{ demo.id }}" class="wrap-collabsible"> <input id="collapsible{{ demo.id }}" class="toggle" type="checkbox"> <label for="collapsible{{ demo.id }}" class="lbl-toggle">Abstract</label>
                <div class="collapsible-content">
                    <div class="content-inner">
                        <p>{{ demo.abstract }}</p>
                    </div>
                </div>
            </div>
        {% endif %}
        {% if demo.url %}
        <div id="video_{{ demo.url }}" class="wrap-collabsible" style="margin-top: 0px; padding-top: 0px; margin-bottom: 0px;"> <input id="collapsiblevideo{{ poster.VideoLink }}" class="toggle" type="checkbox"> 
            <label for="collapsiblevideo{{ demo.url }}" class="lbl-toggle">Video</label>
            <div class="collapsible-content">
                <div class="content-inner">
                    <div class="video-container">
                        <iframe src="https://www.youtube.com/embed/{{ demo.url }}" loading="lazy" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                    </div>
                </div>
            </div>
        </div>                           
        {% endif %}
        {% if j == i %}
        {% else %}
            <hr style="margin: 25px 0 25px 0;">
        {% endif %}
    {% endfor %}
</div>


