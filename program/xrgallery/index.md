---
layout: ieeevr-default
title: "XR Gallery"
subtitle: "IEEE VR 2025"
title_separator: "|"
---

<script type="text/javascript">
    $(document).ready(function(){
		var email = ""; 
		var domain = "ieeevr.org"; 

	    email = "art2025"; 		
		$(".art").html("<span class='text-nowrap'><a href=javascript:location='" + "mail" + "to:" + email + "@" + domain + "'><i class='fas fa-fw fa-envelope-square emailIconSm' style=''></i><i class='emailTextSm'>" + email + "@" + domain + "</a></i></span>");            
	});
</script>

<div>
    <h1 id="call-for-art"> XR Gallery </h1>
      <table class="styled-table">
        <tr>
            <th colspan="4">Day: TBD (Timezone: {{ day.timezone }})</th>
        </tr>                   
        {% assign art = site.data.xrgallery | sort: "id" %}
        {% for gallery in art %}
                <tr>
                    <td class="medLarge"><a href="#{{ gallery.id }}">{{ gallery.id }}</a></td>
                    <td class="medLarge"><a href="#{{ gallery.id }}">{{ gallery.title }}</a></td>
                </tr>
        {% endfor %}
    </table>
    {% endfor %}       
    <div>
        {% for gallery in art %}
            <!-- Workshop title matter -->
            <h2 class="padding_top_xsmall" id="{{ workshop.id }}">Exposition: {{ gallery.title }} ({{ gallery.id }})</h2> 
            <!-- <p class="small">{{ workshop.day }}, {{ workshop.starttime }}-{{ workshop.endtime }} ({{ workshop.timezone }}), Room: {{ workshop.room }}</p>                -->
            <div class="padding_left_medium">
                {% if gallery.website %}
                    <med><b style="color: black;">Website:</b> <a href="{{ gallery.website }}" target="_blank">{{ gallery.website }}</a></med><br />
                {% endif %}
                {% if gallery.promotional_image %}
		            <img class="margin_bottom_small" src={{ "/assets/images/xrgallery/{{ gallery.promotional_image }}" | relative_url }} alt="Slide Template 1">
                {% endif %}
                {% if gallery.video %}
                    <div class="video-container">
                        <iframe src="{{gallery.video}}" title="YouTube video player" frameborder="0" 
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                    </div>
                {% endif %}                
                {% if gallery.abstract %}
                    <div id="{{ gallery.id }}" class="wrap-collabsible"> <input id="collapsible{{ gallery.id }}" class="toggle" type="checkbox"> <label for="collapsible{{ gallery.id }}" class="lbl-toggle">Workshop Description</label>
                        <div class="collapsible-content">
                            <div class="content-inner">
                                <p>{{ gallery.abstract }}</p>
                            </div>
                        </div>
                    </div>
                {% endif %}             
                <!--{% if workshop.agenda %}
                    <div class="content-inner">
                        <p><a href="https://ieeevr.org/2025/assets/{{ workshop.agenda }}" target="_blank">Agenda</a></p>
                    </div>
                {% endif %}                            
                 Only show the 'workshop papers' toggle if there's actually something to show 
                {% assign papers_in_session = false %}
                {% for paper in site.data.workshoppapers %}
                    {% if workshop.id == paper.workshop %}
                        {% assign papers_in_session = true %}
                    {% endif %}
                {% endfor %}
                Show a hideable list of all papers in this workshop
                {% if papers_in_session == true %}
                    <div id="{{ workshop.id }}2" class="wrap-collabsible"> 
                        <input id="collapsible{{ workshop.id }}2" class="toggle" type="checkbox"> 
                        <label for="collapsible{{ workshop.id }}2" class="lbl-toggle">Workshop Papers</label>
                        <div class="collapsible-content">
                            <div class="content-inner">
                                {% for paper in site.data.workshoppapers %}
                                    {% if workshop.id == paper.workshop %}
                                        <h4 id="{{ paper.id }}">{{ paper.title }}</h4>
                                        {% if paper.authors %}
                                            <p><i>{{ paper.authors }}</i></p>
                                        {% else %}
                                            <p><i>Author information coming soon</i></p>
                                        {% endif %}
                                        {% if paper.url %}
                                            <p><med>URL: <a href="{{ paper.url }}" target="_blank">{{ paper.url }}</a></med></p>
                                        {% endif %}
                                        {% if paper.abstract %}
                                            <div id="{{ paper.id }}" class="wrap-collabsible"> <input id="collapsible{{ paper.id }}" class="toggle" type="checkbox"> <label for="collapsible{{ paper.id }}" class="lbl-toggle">Abstract</label>
                                                <div class="collapsible-content">
                                                    <div class="content-inner">
                                                        <p>{{ paper.abstract }}</p>
                                                    </div>
                                                </div>
                                            </div>
                                        {% endif %}
                                    {% endif %}
                                {% endfor %}
                            </div>
                        </div>
                    </div>
                {% endif %}  -->
                </div>         
        {% endfor %}
