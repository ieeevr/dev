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

