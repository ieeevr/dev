---
layout: ieeevr-default
title: "Awards"
---
<script type="text/javascript">
    $(document).ready(function(){
		var email = ""; 
		var domain = "ieeevr.org"; 

        email = "awards2025";  		
		$(".awards").html("<span class='text-nowrap'><a href=javascript:location='" + "mail" + "to:" + email + "@" + domain + "'><i class='fas fa-fw fa-envelope-square emailIcon' style=''></i><i class='emailText'>" + email + "@" + domain + "</a></i></span>");   
        
        $(".awardsSm").html("<span class='text-nowrap'><a href=javascript:location='" + "mail" + "to:" + email + "@" + domain + "'><i class='fas fa-fw fa-envelope-square emailIconSm' style=''></i><i class='emailTextSm'>" + email + "@" + domain + "</a></i></span>"); 
	});
</script>
<h1>Conference Awards Committee IEEE VR 2025 <div class="floatRight"><span class="awardsSm"></span></div></h1>

<h2>Chairs</h2>
<ul>
    <li>Kiyoshi Kiyokawa ‒ Nara Institute of Science and Technology, Japan</li>
    <li>Frank Steinicke ‒ Universität Hamburg, Germany</li>
    <li>Stefania Serafin ‒ Aalborg University, Denmark</li>
    <li>Amine Chellali ‒ Université d'Evry Paris-Saclay, France</li>
</ul>

<h2>Best Papers & Honorable Mention for Best Papers</h2>

<p>The IEEE VR Best Paper Awards honor exceptional papers published and presented at the IEEE VR conference. During the review process, the program committee chairs will choose approximately 3% of submissions to receive an award. Among these chosen submissions, the separate Conference Awards Selection Committee will select the best submissions to receive a Best Paper Award (ca. 1% of total submissions), while a selection of the remaining submissions receive an Honorable Mention Award. Papers that receive an award will be marked in the program, and authors will receive a certificate at the conference.</p>
{% assign award = site.data.awards | where: "type", "Journal" | where: "award", "Best Paper" %}
{% if award.size > 0  %}
<div>
    <h2 id='paper-best' style="text-align: center; color: #00aeef;"><img src= "{{ "/assets/images/awards/best.png" | relative_url }}" title="Best Paper Award" alt="Best Paper Award"> Best Papers</h2>
</div>
{% endif %}    
<div style="padding-bottom:15px;">
    {% for item in award %}     
        {% if item.ptype == 'Journal' %}
            {% assign source = site.data.acceptedpapers %}
            {% assign source2 = site.data.acceptedpaperstvcg %}
        {% endif %}
        {% if item.ptype == 'Conference' %}
            {% assign source = site.data.conferencepapers %}
        {% endif %}
        {% if item.ptype == 'Invited Journal' %}
            {% assign source = site.data.invitedjournalpapers %}
        {% endif %}
        {% for acpaper in source %}
            {% if item.id == acpaper.ids  %} 
                <p class="medLarge" id="paper_{{ acpaper.id }}" style="margin-bottom: 0.3em;">
                    <b>{{ acpaper.title }}</b>
                </p>
                <div><p class="font_70">
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
                </p></div>
                {% if acpaper.abstract %}
                    <div id="{{ acpaper.ids }}" class="wrap-collabsible"> <input id="collapsibleabstract{{ acpaper.ids }}" class="toggle" type="checkbox"> 
                        <label for="collapsibleabstract{{ acpaper.ids }}" class="lbl-toggle">Abstract</label>
                        <div class="collapsible-content">
                            <div class="content-inner">
                                <p>{{ acpaper.abstract }}</p>
                            </div>
                        </div>
                    </div>   
                {% endif %}
            {% endif %}            
        {% endfor %}
        {% for acpaper in source2 %}
            {% if item.id == acpaper.ids  %} 
                <p class="medLarge" id="paper_{{ acpaper.id }}" style="margin-bottom: 0.3em;">
                    <b>{{ acpaper.title }}</b>
                </p>
                <div><p class="font_70">
                    {{ acpaper.contactauthor }}
                </p></div>
                {% if acpaper.abstract %}
                    <div id="{{ acpaper.ids }}" class="wrap-collabsible"> <input id="collapsibleabstract{{ acpaper.ids }}" class="toggle" type="checkbox"> 
                        <label for="collapsibleabstract{{ acpaper.ids }}" class="lbl-toggle">Abstract</label>
                        <div class="collapsible-content">
                            <div class="content-inner">
                                <p>{{ acpaper.abstract }}</p>
                            </div>
                        </div>
                    </div>   
                {% endif %}
            {% endif %}
            
        {% endfor %}
    {% endfor %}
</div>
{% assign award = site.data.awards | where: "type", "Journal" | where: "award", "Honorable Mention" %}
<h2> Honorable Mention for Best Papers </h2>
{% if award.size > 0  %}
<div>
    <h2 id='paper-honorable' style="text-align: center; color: #00aeef;"><img src= "{{ "/assets/images/awards/hm.png" | relative_url }}" title="Best Paper Honorable Mention" alt="Best Paper Honorable Mention"> Best Papers - Honorable Mentions</h2>
</div>
{% endif %}  
<div style="padding-bottom:15px;">
    {% for item in award %}     
        {% if item.ptype == 'Journal' %}
            {% assign source = site.data.acceptedpapers %}
        {% endif %}
        {% if item.ptype == 'Conference' %}
            {% assign source = site.data.conferencepapers %}
        {% endif %}
        {% if item.ptype == 'Invited Journal' %}
            {% assign source = site.data.invitedjournalpapers %}
        {% endif %}
        {% for acpaper in source %}
            {% if item.id == acpaper.ids  %} 
                <p class="medLarge" id="paper_{{ paper.id }}" style="margin-bottom: 0.3em;">
                    <b>{{ acpaper.title }}</b>
                </p>
                <div><p class="font_70">
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
                </p></div>
                {% if acpaper.abstract %}
                    <div id="{{ acpaper.ids }}" class="wrap-collabsible"> <input id="collapsibleabstract{{ acpaper.ids }}" class="toggle" type="checkbox"> 
                        <label for="collapsibleabstract{{ acpaper.ids }}" class="lbl-toggle">Abstract</label>
                        <div class="collapsible-content">
                            <div class="content-inner">
                                <p>{{ acpaper.abstract }}</p>
                            </div>
                        </div>
                    </div>   
                {% endif %}
            {% endif %}
            
        {% endfor %}
    {% endfor %}
</div>

<!-- <h2>Best Posters & Honorable Mention for Best Poster</h2>

<p>The IEEE VR Best Poster Awards honors exceptional posters published and presented at the IEEE VR conference. During the review process, the best poster committee for IEEE VR consists of three distinguished members chosen by the Conference Awards Committee and Poster Chairs, which will select the best posters based on the two-page abstract and the poster presentation during the conference. Posters that receive an award will be marked in the program, and authors will receive a certificate at the conference. </p>
{% assign award = site.data.awards | where: "type", "Journal" | where: "award", "Honorable Mention" %}
<h2>Best Demo & Honorable Mention for Best Demo</h2>

<p>The IEEE VR Best Demo Awards honors exceptional research demos published and presented at the IEEE VR conference. The IEEE VR Demo Chairs rank the accepted demos and recommend approximately 10% of all demos for an award. The best demo committee for IEEE VR consists of three distinguished members chosen by the Conference Awards Committee Chairs and the Demo Chairs. This committee selects one of the demos for the Best Demo Award and one for the Honorable Mention Award. The corresponding authors will receive a certificate at the conference. </p>


<h2>Best 3DUI Contest & Honorable Mention</h2>

<p>The IEEE VR Best 3DUI Contest Submission Awards honors exceptional 3DUI contest submissions published and presented at the IEEE VR conference. The 3DUI contest chairs select one of the submissions for the Best 3DUI Contest Submission Award and one for the Honorable Mention Award. The final decision is based on a combination of the reviews’ scores, scores from experts testing the contest submission during the conference, and the audience scores. The winning team with the highest score will be awarded. Authors will receive a certificate at the conference.</p>


<h2>Best DC Paper & Honorable Mention for Best DC Paper</h2>

<p>The IEEE VR Best Doctoral Consortium (DC) Paper Awards honors exceptional DC papers published and presented at the IEEE VR conference. The best DC paper committee consists of three distinguished members chosen by the Conference Awards Committee Chairs and the DC chairs. The DC chairs recommend 20% of all DC papers for such an award. The best DC committee selects one of these DC papers for Best DC Paper Award and one to receive an Honorable Mention Award. DC papers that receive an award will be marked in the program, and authors will receive a certificate at the conference. </p>


<h2>Best Paper Presentation</h2>

<p>The IEEE VR Best Presentation Awards honor excellent, interesting, and stimulating presentations of research papers at the IEEE VR conference. During the conference, the audience can give a vote for each presentation that they think deserves an award. Approximately 3% of presentations with the highest number of votes receive an award. Among these selected presentations, the top 1% regarding the number of votes, will receive a Best Presentation Award, while the remaining presentations receive an Honorable Mention Award.</p>

-->
