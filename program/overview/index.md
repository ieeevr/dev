---
layout: ieeevr-default
title: "Program Overview"
subtitle: "IEEE VR 2025"
title_separator: "|"
---
<link rel="stylesheet" href="{{ '/assets/css/calendar.css' | relative_url }}?version=20240318">
    
<script>
    const days = ["Saturday", "Sunday", "Monday", "Tuesday", "Wednesday", "Thursday"];

    (function($) {
        $(function() {
            $("#accordion > div").accordion({ header: "h4", heightStyle: "content", active: false, collapsible: true });
        })
    })(jQuery);

   $(document).ready(function(){
        let now = new Date();       
        let start = new Date("March 8, 2025 00:00:00");
        let end = new Date("March 12, 2025 18:00:00");
        let day = days[now.getDay()];

        if (start <= now && now <= end) {             
            switch (day) {
                case "Saturday":                    
                    $( ".preconf" ).show();
                    $('#day1').click();
                case "Sunday":                    
                    $( ".preconf" ).show();
                    $('#day2').click();
                case "Monday":
                    $('#day3').click();
                case "Tuesday":
                    $('#day4').click();
                case "Wednesday":
                    $('#day5').click();
                    break;
                default: 
            }
        } else {            
            $( ".preconf" ).show();
            $('#day1').click();
            $('#day2').click();
            $('#day3').click();
            $('#day4').click();
            $('#day5').click();
        } 
    });   
</script>

<h1 id="schedule-heading">Program Overview</h1>
<p>
    <table class="program-table">
        <thead>
            <tr>
                <th colspan="4">
                IEEE VR 2025, March 8-12 - Select quick links below to skip to a specific day
                <div class="italic" style="text-align: right; float:right;">Updated: 19 February, 2025 </div>
                </th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td class="alignCenter" colspan="4">
                    <a href="{{ "/attend/conference-center-map/" | relative_url }}" target="_blank">Conference Center Map</a>
                </td>
            </tr>
           <tr class="preconf" style="display:none">
                <td class="text-nowrap"><a href="#day1">Saturday<br>2025-03-08</a></td>
                <td>
                    * Workshops<br>
                    * Tutorials<br>
                    * Doctoral Consortium
                </td>
                <td class="text-nowrap"><a href="#day2">Sunday<br>2025-03-09</a></td>
                <td>
                    * Workshops<br>
                    * Tutorials<br>
                    * Future Faculty Forum
                </td>
            </tr>
            <tr>
                <td class="text-nowrap"><a href="#day3">Monday<br>2025-03-10</a></td>
                <td>
                    * Opening & Awards<br>
                    * Keynote Speaker<br>
                    * Papers Sessions<br>
                    <div style="text-indent: -.7em; margin-left: .7em;">
                        * Posters & Research Demos & XR Gallery & 3DUI Contest Demos & Exhibits<br>
                    </div>
                    <div style="text-indent: -.7em; margin-left: .7em;">
                        * Research Demos, 3DUI Contest Demos & Posters<br>
                    </div>
                    * Welcome Reception
                </td>
                <td class="text-nowrap"><a href="#day4">Tuesday<br>2025-03-11</a></td>
                <td>    
                    * Lightning Keynotes<br>
                    * Papers Sessions<br>                
                    <div style="text-indent: -.7em; margin-left: .7em;">
                        * Posters & Research Demos & XR Gallery & 3DUI Contest Demos & Exhibits<br>
                    </div>
					* Gala Dinner
                </td>
            </tr>
            <tr>
                <td class="text-nowrap"><a href="#day5">Wednesday<br>2025-03-12</a></td>
                <td>
                    * Keynote Speaker<br>
                    * Papers Sessions<br>
                    <div style="text-indent: -.7em; margin-left: .7em;">
                        * Posters & Research Demos & XR Gallery & 3DUI Contest Demos & Exhibits<br>
                    </div>
                    * Closing
                </td>
            </tr>
        </tbody>
    </table>
</p>

<div class="notice--info alignCenter bold" style="font-size: 0.9em !important;">
    Please note that all times are given in Saint-Malo, France local time (UTC+1).
</div>
<div class="clear"></div>
<div id="accordion">
    <div>
        <h4 id="day1">Saturday, 8 March 2025</h4>
        <div class="schedule-sat" aria-labelledby="Saturday, 8 March 2025 - Workshop Schedule"> 
            <p class="time-slot" style="grid-row: time-0800;">8:00</p> 
            <div class="session track-registration" style="grid-column: track-0; grid-row: time-0800 / time-1600;">  
                <div class="rotate_reg">             
                    <span class="session-title">Registration:&nbsp;8:00&#8209;16:00&nbsp;&nbsp;&nbsp;&nbsp;</span>
                </div>
            </div>  
<!-- SATURDAY Morning (Part 1) -->			
            <p class="time-slot" style="grid-row: time-0830;">8:30</p>  
             {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'ANIVAE' %}
                    <div class="session session-w3a track-workshop" style="grid-column: track-1; grid-row: time-0830 / time-1000;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>        
                {% endif %}   
            {% endfor %}                  
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'XR Health' %}
                    <div class="session session-w4a track-workshop" style="grid-column: track-2; grid-row: time-0830 / time-1000;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}    
            {% endfor %}               
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'GenAI-XR' %}
                    <div class="session track-workshop" style="grid-column: track-3; grid-row: time-0830 / time-1000;">                    
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}   
            {% endfor %}             
            {% for workshop in site.data.workshops %}   
                {% if workshop.id == 'ENPT-XR' %}
                    <div class="session session-w2a track-workshop" style="grid-column: track-4; grid-row: time-0830 / time-1000;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>         
                {% endif %}     
            {% endfor %} 
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'PerGraVAR' %}
                    <div class="session session-w5a track-workshop" style="grid-column: track-5; grid-row: time-0830 / time-1000;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %}                            
            {% for workshop in site.data.workshops %}    
                {% if workshop.id == 'KEVLAR' %}
                    <div class="session session-w6a track-workshop" style="grid-column: track-6; grid-row: time-0830 / time-1000;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %}     
			{% for workshop in site.data.workshops %}    
                {% if workshop.id == 'LocXR' %}
                    <div class="session session-w6a track-workshop" style="grid-column: track-7; grid-row: time-0830 / time-1000;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %}   
            <div class="session session-w1b track-consortium" style="grid-column: track-11; grid-row: time-0815 / time-0830;">                    
                <span class="session-title"><a href="{{ '/program/doctoral-consortium/' | relative_url }}">Doctoral Consortium (DC) Welcome</a></span>
                <span class="session-time">8:20-8:30</span>
                <span class="session-time">Room: ???</span>
            </div>              
            <p class="time-slot" style="grid-row: time-0830;">8:30</p>    
            {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T1' %}
                    <div class="session session-t1a track-tutorials" style="grid-column: track-8; grid-row: time-0830 / time-1000;">                    
                        <span class="session-title">Tutorial<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: Charcot&nbsp;</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}         
            {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T2' %}
                    <div class="session session-t1a track-tutorials" style="grid-column: track-9; grid-row: time-0830 / time-1000;">                    
                        <span class="session-title">Tutorial<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: Vauban&nbsp;1</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}           
            <div class="session session-w1b track-consortium" style="grid-column: track-11; grid-row: time-0830 / time-1000;">                    
                <span class="session-title"><a href="{{ '/program/doctoral-consortium/' | relative_url }}">DC</a> | Presentations 1-6 (10-min talk + 5-min Q&A for each presentation)</span>
                <span class="session-time">8:30-10:00</span>
                <span class="session-time">Room: La Conchée</span>
            </div>              
            <p class="time-slot" style="grid-row: time-1000;">10:00</p>
            <div class="session session-16 track-all" style="grid-column:  track-1-start / track-10-end; grid-row: time-1000 / time-1030;">
                <span class="session-title">Break (Catered): 10:00-10:30</span>
            </div>                             
            <div class="session session-w1b track-consortium" style="grid-column: track-11; grid-row: time-1000 / time-1030;">                    
                <span class="session-title"><a href="{{ '/program/doctoral-consortium/' | relative_url }}">DC</a> | Break (Catered) (breakout with mentors)</span>
                <span class="session-time">10:00-10:30</span>
                <span class="session-time">Room: La Conchée</span>
            </div>       
<!-- SATURDAY Morning (Part 2) -->		 
             <p class="time-slot" style="grid-row: time-1030;">10:30</p>                                                           
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'ANIVAE' %}
                    <div class="session session-w4b track-workshop" style="grid-column: track-1; grid-row: time-1030 / time-1230;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}    
            {% endfor %}                
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'XR Health' %}
                    <div class="session session-w1b track-workshop" style="grid-column: track-2; grid-row: time-1030 / time-1230;">                    
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}   
            {% endfor %}           
            {% for workshop in site.data.workshops %}   
                {% if workshop.id == 'GenAI-XR' %}
                    <div class="session session-w2b track-workshop" style="grid-column: track-3; grid-row: time-1030 / time-1230;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>         
                {% endif %}     
            {% endfor %}             
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'ENPT-XR' %}
                    <div class="session session-w5b track-workshop" style="grid-column: track-4; grid-row: time-1030 / time-1230;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %}                            
            {% for workshop in site.data.workshops %}    
                {% if workshop.id == 'PerGraVAR' %}
                    <div class="session session-w6b track-workshop" style="grid-column: track-5; grid-row: time-1030 / time-1230;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %}                                      
            {% for workshop in site.data.workshops %}    
                {% if workshop.id == 'KEVLAR' %}
                    <div class="session session-w6b track-workshop" style="grid-column: track-6; grid-row: time-1030 / time-1230;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %}                               
            {% for workshop in site.data.workshops %}    
                {% if workshop.id == 'LocXR' %}
                    <div class="session session-w6b track-workshop" style="grid-column: track-7; grid-row: time-1030 / time-1230;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %} 
             {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T1' %}
                    <div class="session session-t1b track-tutorials" style="grid-column: track-8; grid-row: time-1030 / time-1230;">                    
                        <span class="session-title">Tutorial (cont)<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: Charcot</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}     
             {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T4' %}
                    <div class="session session-t1b track-tutorials" style="grid-column: track-9; grid-row: time-1030 / time-1230;">                    
                        <span class="session-title">Tutorial (cont)<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: Vauban&nbsp;1</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}  
             {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T5' %}
                    <div class="session session-t1b track-tutorials" style="grid-column: track-10; grid-row: time-1030 / time-1230;">                    
                        <span class="session-title">Tutorial (cont)<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: Vauban&nbsp;2</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}  
            <div class="session session-w1b track-consortium" style="grid-column: track-11; grid-row: time-1030 / time-1230;">                    
                <span class="session-title"><a href="{{ '/program/doctoral-consortium/' | relative_url }}">DC</a> | Presentations 7-12 (10-min talk + 5-min Q&A for each presentation)</span>
                <span class="session-time">10:30-12:30</span>
                <span class="session-time">Room: La Conchée</span>
            </div>  
<!-- SATURDAY Lunch -->		          
            <p class="time-slot" style="grid-row: time-1230;">12:30</p> 
            <div class="session session-lunch track-all" style="grid-column: track-1-start / track-10-end; grid-row: time-1230 / time-1400;">
                <span class="session-title">Lunch (Not Catered): 12:30-14:00</span>
            </div>                                           
            <div class="session session-w1b track-consortium" style="grid-column: track-11; grid-row: time-1230 / time-1400;">                 
                <span class="session-title"><a href="{{ '/program/doctoral-consortium/' | relative_url }}">DC</a> | Lunch (Not Catered) (breakout with mentors)</span><br/>
                <span class="session-time">12:30-14:00</span>
                <span class="session-time">Room: ???</span>
            </div>      
<!-- SATURDAY Afternoon (Part 1) -->		    
            <p class="time-slot" style="grid-row: time-1400;">14:00</p>     
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'ARCHERIX' %}
                    <div class="session session-9a track-workshop" style="grid-column: track-1; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>            
                {% endif %}     
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'MASSXR' %}
                    <div class="session session-10a track-workshop" style="grid-column: track-2; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'GEMINI' %}
                    <div class="session session-7a track-workshop" style="grid-column: track-3; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>            
                {% endif %}     
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'ReViSi' %}
                    <div class="session session-8a track-workshop" style="grid-column: track-4; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>              
                {% endif %}     
            {% endfor %} 
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'WISP' %}
                    <div class="session session-11a track-workshop" style="grid-column: track-5; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'NGA' %}
                    <div class="session session-6c track-workshop" style="grid-column: track-6; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}       
            {% endfor %}       
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'IDEATExR' %}
                    <div class="session session-6c track-workshop" style="grid-column: track-7; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}       
            {% endfor %}   
             {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T6' %}
                    <div class="session session-t1b track-tutorials" style="grid-column: track-8; grid-row: time-1400 / time-1600;">                    
                        <span class="session-title">Tutorial (cont)<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: Charcot</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}  
             {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T7' %}
                    <div class="session session-t1b track-tutorials" style="grid-column: track-9; grid-row: time-1400 / time-1600;">                    
                        <span class="session-title">Tutorial (cont)<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: Vauban&nbsp;1</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}  
             {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T8' %}
                    <div class="session session-t1b track-tutorials" style="grid-column: track-10; grid-row: time-1400 / time-1600;">                    
                        <span class="session-title">Tutorial (cont)<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: Vauban&nbsp;2</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}  
            <div class="session session-w1b track-consortium" style="grid-column: track-11; grid-row: time-1400 / time-1600;">                    
                <span class="session-title"><a href="{{ '/program/doctoral-consortium/' | relative_url }}">DC</a> | Presentations 13-20 (10-min talk + 5-min Q&A for each presentation)</span>
                <span class="session-time">14:00-16:00</span>
                <span class="session-time">Room: La Conchée</span>
            </div>         
            <p class="time-slot" style="grid-row: time-1600;">16:00</p>
            <div class="session session-16 track-all" style="grid-column:  track-1-start / track-10-end; grid-row: time-1600 / time-1630;">
                <span class="session-title">Break (Catered): 16:00-16:30</span>
            </div>                  
            <div class="session session-w1b track-consortium" style="grid-column: track-11; grid-row: time-1600 / time-1630;">                
                <span class="session-title"><a href="{{ '/program/doctoral-consortium/' | relative_url }}">DC</a> | Break (Catered) (breakout with mentors)</span>
                <span class="session-time">16:00-16:30</span>
                <span class="session-time">Room: ???</span>
            </div>          
<!-- SATURDAY Afternoon (Part 2) -->	
            <p class="time-slot" style="grid-row: time-1630;">16:30</p>               
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'ARCHERIX' %}
                    <div class="session session-9b track-workshop" style="grid-column: track-1; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>            
                {% endif %}     
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'MASSXR' %}
                    <div class="session session-10b track-workshop" style="grid-column: track-2; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'GEMINI' %}
                    <div class="session session-7b track-workshop" style="grid-column: track-3; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>            
                {% endif %}     
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'ReViSi' %}
                    <div class="session session-8b track-workshop" style="grid-column: track-4; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>              
                {% endif %}     
            {% endfor %}  
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'WISP' %}
                    <div class="session session-11b track-workshop" style="grid-column: track-5; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}     
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'NGA' %}
                    <div class="session session-6d track-workshop" style="grid-column: track-6; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}       
            {% endfor %}        
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'IDEATExR' %}
                    <div class="session session-6d track-workshop" style="grid-column: track-7; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}       
            {% endfor %}                  
             {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T9' %}
                    <div class="session session-t2a track-tutorials" style="grid-column: track-8; grid-row: time-1630 / time-1800;">                    
                        <span class="session-title">Tutorial<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: Charcot</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}                 
             {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T10' %}
                    <div class="session session-t2a track-tutorials" style="grid-column: track-9; grid-row: time-1630 / time-1800;">                    
                        <span class="session-title">Tutorial<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: Vauban&nbsp;1</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}             
             {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T8' %}
                    <div class="session session-t2a track-tutorials" style="grid-column: track-10; grid-row: time-1630 / time-1800;">                    
                        <span class="session-title">Tutorial<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: Vauban&nbsp;2</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %} 
            <div class="session session-w1b track-consortium" style="grid-column: track-11; grid-row: time-1630 / time-1800;">                    
                <span class="session-title"><a href="{{ '/program/doctoral-consortium/' | relative_url }}">DC</a> | Presentations 21-24 (10-min talk + 5-min Q&A for each presentation)</span>
                <span class="session-time">16:30-18:00</span>
                <span class="session-time">Room: La Conchée</span>
            </div>  
            <p class="time-slot" style="grid-row: time-1700;">17:00</p>                 
            <div class="session session-w1b track-consortium" style="grid-column: track-11; grid-row: time-1800 / time-1830;">                    
                <span class="session-title"><a href="{{ '/program/doctoral-consortium/' | relative_url }}">DC</a> | Breakout with mentors</span>
                <span class="session-time">16:30-18:00</span>
                <span class="session-time">Room: ???</span>
            </div> 
			<p class="time-slot" style="grid-row: time-1800;">18:00</p>  			
        </div> 
    </div>
	<div>
        <h4 id="day2">Sunday, 9 March 2025</h4> 
        <div class="schedule-sun" aria-labelledby="Sunday, 9 March 2029 - Workshop Schedule">  
<!-- SUNDAY Morning (Part 1) -->
        <p class="time-slot" style="grid-row: time-0800;">8:00</p> 
            <div class="session track-registration" style="grid-column: track-0; grid-row: time-0800 / time-1600;">  
                <div class="rotate_reg">             
                    <span class="session-title">Registration:&nbsp;8:00&#8209;16:00&nbsp;&nbsp;&nbsp;&nbsp;</span>
                </div>
            </div>   
            <p class="time-slot" style="grid-row: time-0830;">8:30</p>                         
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'VR-HSA' %}
                    <div class="session session-w15a track-workshop" style="grid-column: track-1; grid-row: time-0830 / time-1000;"> 
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'XRMemory' %}
                    <div class="session session-w12a track-workshop" style="grid-column: track-2; grid-row: time-0830 / time-1000;">                        
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %} 
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'WSR' %}
                    <div class="session session-w13a track-workshop" style="grid-column: track-3; grid-row: time-0830 / time-1000;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>         
                {% endif %}      
            {% endfor %}  
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'SIC-XR' %}
                    <div class="session session-w16a track-workshop" style="grid-column: track-4; grid-row: time-0830 / time-1000;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}  
            {% for workshop in site.data.workshops %}   
                {% if workshop.id == 'ReDigiTS' %}
                    <div class="session session-w17a track-workshop" style="grid-column: track-5; grid-row: time-0830 / time-1000;">                   
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}  
            {% for workshop in site.data.workshops %}   
                {% if workshop.id == 'VHCIE' %}
                    <div class="session session-w17a track-workshop" style="grid-column: track-6; grid-row: time-0830 / time-1000;">                   
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}  
            {% for workshop in site.data.workshops %}   
                {% if workshop.id == 'NIDIT' %}
                    <div class="session session-w17a track-workshop" style="grid-column: track-7; grid-row: time-0830 / time-1000;">                   
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}                          
             {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T11' %}
                    <div class="session session-t3a track-tutorials" style="grid-column: track-8; grid-row: time-0830 / time-1000;">                    
                        <span class="session-title">Tutorial<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">8:30-10:00</span>
                        <span class="session-time">Room: Vauban&nbsp;2</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}                  
             <div class="session session-f31 track-f3" style="grid-column: track-9; grid-row: time-0830 / time-0845;">                        
                <span class="session-title"><a href="{{ '/program/future-faculty-forum/' | relative_url }}">Future Faculty Forum (F3)</a></span>
            </div>    
            <p class="time-slot" style="grid-row: time-0845;">8:45</p>         
            <div class="session session-f32 track-f3" style="grid-column: track-9; grid-row: time-0845 / time-0900;">                        
                <span class="session-title"><a href="{{ '/program/future-faculty-forum/' | relative_url }}">F3</a> | Welcome & Opening Remarks</span>
                <span class="session-time">8:45-9:00</span>
                <span class="session-time">Room: La Conchée</span>
            </div>                
            <p class="time-slot" style="grid-row: time-0900;">9:00</p>           
            <div class="session session-f33 track-f3" style="grid-column: track-9; grid-row: time-0900 / time-1000;">  
                <span class="session-title"><a href="{{ '/program/future-faculty-forum/' | relative_url }}">F3</a> | Tutorial: Professor Application Process</span>                      
                <span class="session-time">9:00-10:00</span>
                <span class="session-time">Room: La Conchée</span>
            </div>            
            <p class="time-slot" style="grid-row: time-1000;">10:00</p>
            <div class="session session-b track-all" style="grid-column:  track-1-start / track-9-end; grid-row: time-1000 / time-1030;">
                <span class="session-title">Break (Catered): 10:00-10:30</span><br />
            </div> 
<!-- SUNDAY Morning (Part 2) -->
            <p class="time-slot" style="grid-row: time-1030;">10:30</p>             
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'VR-HSA' %}
                    <div class="session session-w14b track-workshop" style="grid-column: track-1; grid-row: time-1030 / time-1230;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>        
                {% endif %}      
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'XR Memory' %}
                    <div class="session session-w15b track-workshop" style="grid-column: track-2; grid-row: time-1030 / time-1230;"> 
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'WSR' %}
                    <div class="session session-w12b track-workshop" style="grid-column: track-3; grid-row: time-1030 / time-1230;">                        
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %} 
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'SIC-XR' %}
                    <div class="session session-w13b track-workshop" style="grid-column: track-4; grid-row: time-1030 / time-1230;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>         
                {% endif %}      
            {% endfor %}  
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'ReDigiTS' %}
                    <div class="session session-w16b track-workshop" style="grid-column: track-5; grid-row: time-1030 / time-1230;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}  
            {% for workshop in site.data.workshops %}   
                {% if workshop.id == 'VHCIE' %}
                    <div class="session session-w17b track-workshop" style="grid-column: track-6; grid-row: time-1030 / time-1230;">                   
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}        
			{% for workshop in site.data.workshops %}   
                {% if workshop.id == 'NIDIT' %}
                    <div class="session session-w17b track-workshop" style="grid-column: track-7; grid-row: time-1030 / time-1230;">                   
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}   			
            {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T12' %}
                    <div class="session session-t3b track-tutorials" style="grid-column: track-8; grid-row: time-1030 / time-1230;">                    
                        <span class="session-title">Tutorial (cont)<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">10:30-12:30</span>
                        <span class="session-time">Room: Vauban&nbsp;2</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}   
            <div class="session session-f34 track-f3" style="grid-column: track-9; grid-row: time-1030 / time-1115;">                        
                <span class="session-title"><a href="{{ '/program/future-faculty-forum/' | relative_url }}">F3</a> | Panel 1: Differences in Universities (Geo, Research vs. Teaching Alloc.)</span>
                <span class="session-time">10:30-11:15</span>
                <span class="session-time">Room: La Conchée</span>
            </div>      
            <p class="time-slot" style="grid-row: time-1115;">11:15</p>          
            <div class="session session-f35 track-f3" style="grid-column: track-9; grid-row: time-1115 / time-1200;">                        
                <span class="session-title"><a href="{{ '/program/future-faculty-forum/' | relative_url }}">F3</a> | Panel 2: Lab Formation & Management</span>
                <span class="session-time">11:15-12:00</span>
                <span class="session-time">Room: La Conchée</span>
            </div>   
            <p class="time-slot" style="grid-row: time-1200;">12:30</p>
            <div class="session session-l track-all" style="grid-column: track-1-start / track-9-end; grid-row: time-1230 / time-1400;">
                <span class="session-title">Lunch (Not Catered): 12:30&#8209;14:00</span>
            </div>   
<!-- SUNDAY Afternoon (Part 1) -->                     
            <p class="time-slot" style="grid-row: time-1400;">14:00</p>             
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'SIVE' %}
                    <div class="session session-10 track-workshop" style="grid-column: track-1; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>            
                {% endif %}      
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'TrainingXR' %}
                    <div class="session session-11 track-workshop" style="grid-column: track-2; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}               
            {% for workshop in site.data.workshops %} 
                {% if workshop.id == 'XRIOS' %}
                    <div class="session session-8 track-workshop" style="grid-column: track-3; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>            
                {% endif %}      
            {% endfor %}  
            {% for workshop in site.data.workshops %}   
                {% if workshop.id == 'MRSI' %}
                    <div class="session session-9 track-workshop" style="grid-column: track-4; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>              
                {% endif %}      
            {% endfor %}  
            {% for workshop in site.data.workshops %}   
                {% if workshop.id == 'PCMIW' %}
                    <div class="session session-12 track-workshop" style="grid-column: track-5; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'IVL' %}
                    <div class="session session-13 track-workshop" style="grid-column: track-6; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}       
            {% endfor %}         
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'XRaccess' %}
                    <div class="session session-13 track-workshop" style="grid-column: track-7; grid-row: time-1400 / time-1600;">
                        <span class="session-title">Workshop<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">14:00-16:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}       
            {% endfor %}
            {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'T13' %}
                    <div class="session session-t3b track-tutorials" style="grid-column: track-8; grid-row: time-1400 / time-1600;">                    
                        <span class="session-title">Tutorial<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">14:00-15:30</span>
                        <span class="session-time">Room: Vauban&nbsp;2</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %}     
            <div class="session session-20 track-f3" style="grid-column: track-9; grid-row: time-1415 / time-1530;">                        
                <span class="session-title"><a href="{{ '/program/future-faculty-forum/' | relative_url }}">F3</a> | Tutorial: Review & Critique of Application Materials (Research, Teaching & Diversity Statements)</span>
                <span class="session-time">14:15-15:30</span>
                <span class="session-time">Room: La Conchée</span>
            </div>            
            <p class="time-slot" style="grid-row: time-1600;">16:00</p>
            <div class="session session-16 track-all" style="grid-column: track-1 / track-9; grid-row: time-1600 / time-1630;">
                <span class="session-title">Break (Catered): 16:00-16:30</span>
            </div>  
<!-- SUNDAY Afternoon (Part 2) -->  
            <p class="time-slot" style="grid-row: time-1630;">16:30</p>              
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'SIVE' %}
                    <div class="session session-10 track-workshop" style="grid-column: track-1; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>            
                {% endif %}      
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'TrainingXR' %}
                    <div class="session session-11 track-workshop" style="grid-column: track-2; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}  
            {% for workshop in site.data.workshops %} 
                {% if workshop.id == 'XRIOS' %}
                    <div class="session session-8 track-workshop" style="grid-column: track-3; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>            
                {% endif %}      
            {% endfor %}  
            {% for workshop in site.data.workshops %}   
                {% if workshop.id == 'MRSI' %}
                    <div class="session session-12 track-workshop" style="grid-column: track-4; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}      
            {% endfor %}   
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'PCMIW' %}
                    <div class="session session-13 track-workshop" style="grid-column: track-5; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}       
            {% endfor %}       
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'IVL' %}
                    <div class="session session-13 track-workshop" style="grid-column: track-6; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}       
            {% endfor %} 
            {% for workshop in site.data.workshops %}  
                {% if workshop.id == 'XR Access' %}
                    <div class="session session-13 track-workshop" style="grid-column: track-7; grid-row: time-1630 / time-1800;">
                        <span class="session-title">Workshop (cont)<br/><a href="{{ '/program/workshop/' | relative_url }}#{{ workshop.id }}">{{ workshop.title }} ({{ workshop.id }})</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: {{ workshop.room }}</span>
                        <span class="session-presenter"><br />{{ workshop.organiser }}</span>
                    </div>
                {% endif %}       
            {% endfor %}    
            {% for tutorial in site.data.tutorials %}  
                {% if tutorial.id == 'Art' %}
                    <div class="session session-t3b track-tutorials" style="grid-column: track-8; grid-row: time-1630 / time-1800;">                    
                        <span class="session-title">Tutorial<br /><a href="{{ '/program/tutorials/' | relative_url }}#{{ tutorial.id }}">{{ tutorial.title }}</a></span><br/>
                        <span class="session-time">16:30-18:00</span>
                        <span class="session-time">Room: Vauban&nbsp;2</span>
                        <span class="session-presenter"><br />{{ tutorial.authors }}</span>
                    </div>
                {% endif %}   
            {% endfor %} 
            <div class="session session-22 track-f3" style="grid-column: track-9; grid-row: time-1600 / time-1645;">                        
                <span class="session-title"><a href="{{ '/program/future-faculty-forum/' | relative_url }}">F3</a> | Speed Advising</span>
                <span class="session-time">16:00-16:45</span>
                <span class="session-time">Room: La Conchée</span>
            </div>          
            <p class="time-slot" style="grid-row: time-1630;">16:30</p>               
            <p class="time-slot" style="grid-row: time-1645;">16:45</p>   
            <div class="session session-23 track-f3" style="grid-column: track-9; grid-row: time-1645 / time-1700;">                        
                <span class="session-title"><a href="{{ '/program/future-faculty-forum/' | relative_url }}">F3</a> | Closing Remarks & Feedback for Future F3 Events</span>
                <span class="session-time">16:45-17:00</span>
                <span class="session-time">Room: La Conchée</span>
            </div>             
            <p class="time-slot" style="grid-row: time-1800;">18:00</p>  
			<div class="session track-XRgallery" style="grid-column: track-10; grid-row: time-0800 / time-1800;">  
                <div class="rotate_reg">             
                    <span class="session-title">XR Gallery:&nbsp;8:00&#8209;18:00&nbsp;&nbsp;&nbsp;&nbsp;</span>
                </div>
            </div>   
        </div> 
    </div> 
    <!--    <div>
        <h4 id="day3">Monday, 18 March 2024</h4>
        <div class="schedule-mon" aria-labelledby="Monday, 18 March 2024 - Main Conference">  
            <p class="time-slot" style="grid-row: time-0800;">8:00</p> 
            <div class="session track-registration" style="grid-column: track-0; grid-row: time-0800 / time-1830;"> 
                <div class="rotate_reg">             
                    <span class="session-title">Registration:&nbsp;8:00&#8209;18:30&nbsp;&nbsp;&nbsp;&nbsp;</span>
                </div>
            </div> 
            <p class="time-slot" style="grid-row: time-0830;">8:30</p>
            <div class="session track-main" style="grid-column: track-1-start / track-3-end; grid-row: time-0830 / time-0945;">
                <span class="session-title">Opening & Awards</span>
                <span class="session-time">8:30-9:45</span>
                <span class="session-time">Room: Fantasia Ballroom H</span>
            </div>            
            <p class="time-slot" style="grid-row: time-0945;">9:45</p>
            <div class="session track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-0945 / time-1015;">
                <span class="session-title">Break (Catered): 9:45-10:15</span>
            </div> 
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-0945 / time-1015;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">, 3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">9:45-10:15</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div>                         
            <p class="time-slot" style="grid-row: time-1015;">10:15</p>
            <div class="session track-keynote" style="grid-column: track-1-start / track-3-end; grid-row: time-1015 / time-1115;">
                <span class="session-title">Keynote Speaker<br/><a href="{{ '/program/keynote-speakers/' | relative_url }}#keynote-azenkot">Prof. Shiri Azenkot</a></span>                
                <span class="session-title"><a href="{{ '/program/keynote-speakers/' | relative_url }}#keynote-azenkot">XR Access: Making Virtual and Augmented Reality Accessible to People with Disabilities</a></span>
                <span class="session-time">10:15-11:15</span>   
                <span class="session-time">Room: Fantasia Ballroom H</span>             
            </div> 
            <p class="time-slot" style="grid-row: time-1115;">11:15</p>  
            <div class="session track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1115 / time-1130;">
                <span class="session-title">Stretch Break (Not Catered): 11:15-11:30</span>
            </div>             
            <p class="time-slot" style="grid-row: time-1130;">11:30</p>
            {% for session in site.data.specialsessions %}  
                {% if session.id == 'SS1' %}
                 <div class="session track-special-session" style="grid-column: track-1-start / track-3-end; grid-row: time-1130 / time-1230;">
                    <span class="session-title">Special Session</span>
                    <span class="session-title"><a href="{{ '/program/special-sessions/' | relative_url }}#SS1">{{ session.title }}</a></span>
                    <span class="session-time">{{ session.start }}-{{ session.end }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div> 
                {% endif %}   
            {% endfor %}                         
            <p class="time-slot" style="grid-row: time-1230;">12:30</p>
            <div class="session track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1230 / time-1330;">
                <span class="session-title">Lunch (Not Catered): 12:30-13:30</span>
            </div>  
            <p class="time-slot" style="grid-row: time-1300;">13:00</p>
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-1300 / time-1330;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">13:00-13:30</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div>                        
            <p class="time-slot" style="grid-row: time-1330;">13:30</p>  
            <div class="session track-demos" style="grid-column: track-1-start / track-3-end; grid-row: time-1330 / time-1400;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a> and <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> Fast Forward</span>
                <span class="session-time">13:30-14:00</span>
                <span class="session-time">Room: Fantasia Ballroom H</span>
            </div>  
            <p class="time-slot" style="grid-row: time-1400;">14:00</p>
            {% for session in site.data.sessions %}  
                {% if session.id == 'MO1G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-1400 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#MO1G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %} 
             {% for session in site.data.sessions %}  
                {% if session.id == 'MO1H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-1400 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#MO1H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %} 
            {% for session in site.data.sessions %}  
                {% if session.id == 'MO1J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-1400 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#MO1J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}                
            <p class="time-slot" style="grid-row: time-1500;">15:00</p>
            <div class="session track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1500 / time-1530;">
                <span class="session-title">Break (Catered): 15:00-15:30</span>
            </div>    
            <div class="session session-6 track-pd3dui" style="grid-column: track-4-start; grid-row: time-1500 / time-1530;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">15:00-15:30</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div>  
            <p class="time-slot" style="grid-row: time-1530;">15:30</p>
            {% for session in site.data.sessions %}  
                {% if session.id == 'MO2G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-1530 / time-1700;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#MO2G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'MO2H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-1530 / time-1700;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#MO2H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'MO2J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-1530 / time-1700;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#MO2J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}               
            <p class="time-slot" style="grid-row: time-1700;">17:00</p>                
            <div class="session track-pd3dui" style="padding-bottom: 10px; grid-column: track-4-start; grid-row: time-1700 / time-1730;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">17:00-17:30</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div>
            <p class="time-slot" style="grid-row: time-1730;">17:30</p> 
            <div class="session track-main" style="grid-column: track-1-start / track-3-end; grid-row: time-1700 / time-1830;">
                <span class="session-title">Welcome Reception</span>
                <span class="session-time">17:00-18:30</span>
                <span class="session-time">Room: Sorcerer's Apprentice Lobby and Ballroom</span>
            </div>  
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-1700 / time-1900;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">17:00-19:00</span>
                <span class="session-time">Room: Sorcerer's Apprentice Ballroom</span>
            </div>
        </div> 
    </div>
    <div>
        <h4 id="day4">Tuesday, 19 March 2024</h4>
        <div class="schedule-tue" aria-labelledby="Tuesday, 19 March 2024 - Main Conference">   
            <p class="time-slot" style="grid-row: time-0800;">8:00</p> 
            <div class="session track-registration" style="grid-column: track-0; grid-row: time-0800 / time-1600;">            
                <div class="rotate_reg">             
                    <span class="session-title">Registration:&nbsp;8:00&#8209;16:00&nbsp;&nbsp;&nbsp;&nbsp;</span>
                </div>  
            </div> 
            <p class="time-slot" style="grid-row: time-0830;">8:30</p>                      
            {% for session in site.data.sessions %}  
                {% if session.id == 'TU1G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-0830 / time-0945;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TU1G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TU1H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-0830 / time-0945;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TU1H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TU1J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-0830 / time-0945;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TU1J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}   
            <p class="time-slot" style="grid-row: time-0945;">9:45</p>  
            <div class="session track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-0945 / time-1015;">
                <span class="session-title">Break (Catered): 9:45-10:15</span>
            </div> 
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-0945 / time-1015;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">9:45-10:15</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div>     
            <p class="time-slot" style="grid-row: time-1015;">10:15</p>            
             <div class="session track-keynote" style="grid-column: track-1-start / track-3-end; grid-row: time-1015 / time-1115;">
                <span class="session-title">Keynote Speaker<br/><a href="{{ '/program/keynote-speakers/' | relative_url }}#keynote-tschanz">Michael Tschanz</a></span>                
                <span class="session-title"><a href="{{ '/program/keynote-speakers/' | relative_url }}#keynote-tschanz">Disney's Industrial Controls Design and Data Analytics Ecosystem</a></span>
                <span class="session-time">10:15-11:15</span> 
                <span class="session-time">Room: Fantasia Ballroom H</span>               
            </div> 
            <p class="time-slot" style="grid-row: time-1115;">11:15</p>  
            <div class="session track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1115 / time-1130;">
                <span class="session-title">Stretch Break (Not Catered): 11:15-11:30</span>
            </div> 
            <p class="time-slot" style="grid-row: time-1130;">11:30</p>
            {% for session in site.data.specialsessions %}  
                {% if session.id == 'SS2' %}
                    <div class="session track-special-session" style="grid-column: track-1-start / track-3-end; grid-row: time-1130 / time-1230;">
                        <span class="session-title">Special Session</span>
                        <span class="session-title"><a href="{{ '/program/special-sessions/' | relative_url }}#SS2">{{ session.title }}</a></span>
                        <span class="session-time">{{ session.start }}-{{ session.end }}</span>
                        <span class="session-time">Room: {{ session.room }}</span>
                    </div> 
                {% endif %}   
            {% endfor %}  
            <p class="time-slot" style="grid-row: time-1230;">12:30</p>
            <div class="session track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1230 / time-1330;">
                <span class="session-title">Lunch (Not Catered): 12:30-13:30</span>
            </div>  
            <p class="time-slot" style="grid-row: time-1300;">13:00</p>
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-1300 / time-1330;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">13:00-13:30</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div>   
            <p class="time-slot" style="grid-row: time-1330;">13:30</p>  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TU2G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-1330 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TU2G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TU2H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-1330 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TU2H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TU2J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-1330 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TU2J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}   
            <p class="time-slot" style="grid-row: time-1500;">15:00</p>
            <div class="session track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1500 / time-1530;">
                <span class="session-title">Break (Catered): 15:00-15:30</span>
            </div>    
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-1500 / time-1530;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">15:00-15:30</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div>                 
            {% for session in site.data.sessions %}  
                {% if session.id == 'TU3G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-1530 / time-1700;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TU3G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TU3H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-1530 / time-1700;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TU3H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TU3J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-1530 / time-1700;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TU3J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}   
            <p class="time-slot" style="grid-row: time-1700;">17:00</p>                
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-1700 / time-1730;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">17:00-17:30</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div>
        </div> 
    </div>
    <div>
        <h4 id="day5">Wednesday, 20 March 2024</h4>
        <div class="schedule-wed" aria-labelledby="Wednesday, 20 March 2024 - Main Conference">   
            <p class="time-slot" style="grid-row: time-0800;">8:00</p> 
            <div class="session track-registration" style="grid-column: track-0; grid-row: time-0800 / time-1600;"> 
                <div class="rotate_reg">             
                    <span class="session-title">Registration:&nbsp;8:00&#8209;16:00&nbsp;&nbsp;&nbsp;&nbsp;</span>
                </div>  
            </div>   
            <p class="time-slot" style="grid-row: time-0830;">8:30</p>            
             {% for session in site.data.sessions %}  
                {% if session.id == 'WE1G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-0830 / time-0945;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE1G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE1H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-0830 / time-0945;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE1H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE1J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-0830 / time-0945;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE1J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}     
            <p class="time-slot" style="grid-row: time-0945;">9:45</p>
            <div class="session session-4 track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-0945 / time-1015;">
                <span class="session-title">Break (Catered): 9:45-10:15</span>
            </div>  
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-0945 / time-1015;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">9:45-10:15</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div>   
            <p class="time-slot" style="grid-row: time-1015;">10:15</p> 
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE2G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-1015 / time-1115;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE2G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE2H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-1015 / time-1115;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE2H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE2J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-1015 / time-1115;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE2J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}    
            <p class="time-slot" style="grid-row: time-1115;">11:15</p>
            <div class="session session-6 track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1115 / time-1130;">
                <span class="session-title">Stretch Break (Not Catered): 11:15-11:30</span>
            </div> 
            <p class="time-slot" style="grid-row: time-1130;">11:30</p>  
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE3G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-1130 / time-1230;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE3G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE3H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-1130 / time-1230;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE3H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE3J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-1130 / time-1230;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE3J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}    
            <p class="time-slot" style="grid-row: time-1230;">12:30</p>
            <div class="session session-8 track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1230 / time-1330;">
                <span class="session-title">Lunch (Not Catered): 12:30-13:30</span>
            </div> 
            <p class="time-slot" style="grid-row: time-1300;">13:00</p>
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-1300 / time-1330;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">13:00-13:30</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div> 
            <p class="time-slot" style="grid-row: time-1330;">13:30</p>
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE4G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-1330 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE4G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE4H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-1330 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE4H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'WE4J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-1330 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#WE4J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}    
            <p class="time-slot" style="grid-row: time-1500;">15:00</p> 
            <div class="session session-12 track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1500 / time-1530;">
                <span class="session-title">Break (Catered): 15:00-15:30</span>
            </div>     
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-1500 / time-1530;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">15:00-15:30</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div>             
            <p class="time-slot" style="grid-row: time-1530;">15:30</p> 
            {% for session in site.data.specialsessions %}  
                {% if session.id == 'SS3' %}
                    <div class="session track-special-session" style="grid-column: track-1-start / track-3-end; grid-row: time-1530 / time-1615;">
                        <span class="session-title">Special Session</span>
                        <span class="session-title"><a href="{{ '/program/special-sessions/' | relative_url }}#SS3">{{ session.title }}</a></span>
                        <span class="session-time">{{ session.start }}-{{ session.end }}</span>
                        <span class="session-time">Room: {{ session.room }}</span>
                    </div> 
                {% endif %}   
            {% endfor %}  
            <p class="time-slot" style="grid-row: time-1700;">17:00</p>                
            <div class="session track-pd3dui" style="grid-column: track-4-start; grid-row: time-1700 / time-1730;">
                <span class="session-title"><a href="{{ '/program/demos/' | relative_url }}">Research Demos</a>, <a href="{{ '/program/3dui-contest/' | relative_url }}">3DUI Contest Demos</a> & <a href="{{ '/program/posters/' | relative_url }}">Posters</a></span>
                <span class="session-time">17:00-17:30</span>
                <span class="session-time">Sorcerer's Apprentice BR</span>
            </div> 
            <p class="time-slot" style="grid-row: time-1900;">19:00</p>                
            <div class="session track-main" style="grid-column: track-1-start / track-3-end; grid-row: time-1900 / time-2015;">
                <span class="session-title">Conference Banquet with Keynote Speaker</span>
                <span class="session-title"><a href="{{ '/program/keynote-speakers/' | relative_url }}#keynote-richir">Prof. Simon Richir</a></span>
                <span class="session-title"><a href="{{ '/program/keynote-speakers/' | relative_url }}#keynote-richir">The Laval Phenomenon: A Deep Dive into France's VR Capital</a></span>
                <span class="session-time">19:00-20:15</span>
                <span class="session-track">Fantasia Ballroom</span>
            </div> 
            <p class="time-slot" style="grid-row: time-2015;">20:15</p>                
            <div class="session track-fireworks" style="grid-column: track-1-start / track-3-end; grid-row: time-2015 / time-2100;">
                <span class="session-title">Dessert + Fireworks Viewing</span>  
                <span class="session-time">20:15-21:00</span>
                <span class="session-track">Porte Cochére</span>
            </div>             
        </div> 
    </div>
    <div>
        <h4 id="day6">Thursday, 21 March 2024</h4>
        <div class="schedule-thu" aria-labelledby="Thursday, 21 March 2024 - Main Conference">   
            <p class="time-slot" style="grid-row: time-0830;">8:30</p> 
            <div class="session track-registration" style="grid-column: track-0; grid-row: time-0830 / time-1530;">            
                <div class="rotate_reg">             
                    <span class="session-title">Registration:&nbsp;8:30&#8209;15:30&nbsp;&nbsp;&nbsp;&nbsp;</span>
                </div>  
            </div>   
            <p class="time-slot" style="grid-row: time-0830;">8:30</p>
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH1G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-0830 / time-0945;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH1G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH1H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-0830 / time-0945;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH1H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH1J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-0830 / time-0945;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH1J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}    
            <p class="time-slot" style="grid-row: time-0945;">9:45</p>  
            <div class="session session-4 track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-0945 / time-1015;">
                <span class="session-title">Break (Catered): 9:45-10:15</span>
            </div>  
            <p class="time-slot" style="grid-row: time-1015;">10:15</p>                      
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH2G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-1015 / time-1115;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH2G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH2H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-1015 / time-1115;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH2H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH2J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-1015 / time-1115;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH2J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}    
            <p class="time-slot" style="grid-row: time-1115;">11:15</p>
            <div class="session session-6 track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1115 / time-1130;">
                <span class="session-title">Stretch Break (Not Catered): 11:15-11:30</span>
            </div> 
            <p class="time-slot" style="grid-row: time-1130;">11:30</p>                                  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH3G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-1130 / time-1230;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH3G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH3H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-1130 / time-1230;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH3H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH3J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-1130 / time-1230;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH3J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}    
            <p class="time-slot" style="grid-row: time-1230;">12:30</p>
            <div class="session session-8 track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1230 / time-1330;">
                <span class="session-title">Lunch (Not Catered): 12:30-13:30</span>
            </div> 
            <p class="time-slot" style="grid-row: time-1330;">13:30</p>                                      
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH4G' %}
                <div class="session track-papers" style="grid-column: track-1-start / track-1-end; grid-row: time-1330 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH4G">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH4H' %}
                <div class="session track-papers" style="grid-column: track-2-start / track-2-end; grid-row: time-1330 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH4H">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}  
            {% for session in site.data.sessions %}  
                {% if session.id == 'TH4J' %}
                <div class="session track-papers" style="grid-column: track-3-start / track-3-end; grid-row: time-1330 / time-1500;">
                    <span class="session-title"><a href="{{ '/program/papers/' | relative_url }}#TH4J">{{ session.id }}<br>{{ session.name }}</a></span>
                    <span class="session-time">{{ session.starttime }}-{{ session.endtime }}</span>
                    <span class="session-time">Session Chair: {{ session.sessionchair }}</span>
                    <span class="session-time">Room: {{ session.room }}</span>
                </div>  
                {% endif %}   
            {% endfor %}    
            <p class="time-slot" style="grid-row: time-1500;">15:00</p>  
            <div class="session session-12 track-all" style="grid-column: track-1-start / track-3-end; grid-row: time-1500 / time-1530;">
                <span class="session-title">Break (Catered): 15:00-15:30</span>
            </div>  
            <p class="time-slot" style="grid-row: time-1530;">15:30</p>   
            <div class="session session-11 track-main" style="grid-column: track-1-start / track-3-end; grid-row: time-1530 / time-1700;">
                <span class="session-title">Closing & Awards</span>
                <span class="session-time">15:30-17:00</span>
                <span class="session-time">Room: Fantasia Ballroom H</span>
            </div>            
        </div> -->
    </div>
</div>