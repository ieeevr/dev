---
layout: ieeevr-default
title: "XR Gallery"
subtitle: "IEEE VR 2025"
title_separator: "|"
---


<div>
    <h1 id="call-for-art"> XR Gallery </h1>
      <table class="styled-table">
        <tr>
            <th colspan="4">Day: TBD (Timezone: (Saint-Malo, France UTC+1))</th>
        </tr>                   
        {% assign art = site.data.xrgallery | sort: "id" %}
        {% for gallery in art %}
                <tr>
                    <td class="medLarge"><a href="#{{ gallery.id }}">{{ gallery.id }}</a></td>
                    <td class="medLarge"><a href="#{{ gallery.id }}">{{ gallery.title }}</a></td>
                </tr>
        {% endfor %}
    </table>     
    <div>
        {% for gallery in art %}
            <!-- gallery title matter -->
            <h2 class="padding_top_xsmall" id="{{ gallery.id }}">Exposition: {{ gallery.title }} ({{ gallery.id }})</h2> 
            <!-- <p class="small">{{ gallery.day }}, {{ gallery.starttime }}-{{ gallery.endtime }} ({{ gallery.timezone }}), Room: {{ gallery.room }}</p>                -->
            <div class="padding_left_medium">
                <!--{% if gallery.website %}
                    <med><b style="color: black;">Website:</b> <a href="{{ gallery.website }}" target="_blank">{{ gallery.website }}</a></med><br />
                {% endif %}-->
                <!--{% if gallery.artist %}
                    {% assign authornames = tutorial.gallery.artist | split: "/" %}
                    {% for name in authornames %}
                        <span class='bold'>{{ name }} </span><br />
                    {% endfor %}
                {% endif%}-->
                <!--{% if gallery.image %}
		            <img src={{ "/assets/images/xrgallery/"+"{{ gallery.image }}" | relative_url }} alt="Slide Template 1">
                {% endif %}-->
                <!--{% if gallery.video %}
                    <div class="video-container">
                        <iframe src="{{gallery.video}}" title="YouTube video player" frameborder="0" 
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                    </div>
                {% endif %}                
                {% if gallery.abstract %}
                    <div id="{{ gallery.id }}" class="wrap-collabsible"> <input id="collapsible{{ gallery.id }}" class="toggle" type="checkbox"> <label for="collapsible{{ gallery.id }}" class="lbl-toggle">gallery Description</label>
                        <div class="collapsible-content">
                            <div class="content-inner">
                                <p>{{ gallery.abstract }}</p>
                            </div>
                        </div>
                    </div>
                {% endif %}     -->        
            </div>         
        {% endfor %}
