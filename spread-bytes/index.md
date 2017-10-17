---
layout: default
---
<!-- Main -->
<div id="main" class="wrapper style1">
    <div class="container">
        {% for section in site.data.sections %}
            {% if section.name == 'spread-bytes' %}
                <header class="major major-{{section.color}}">      
            {% endif %}
        {% endfor %}
            {% for section in site.data.sections %}
                {% if section.name == 'spread-bytes' %}
                    <h2>Welcome to {{ section.title }}</h2>
                    {% for info in section.infos %}
                        <p>{{ info }}</p>
                    {% endfor %}        
                {% endif %}
            {% endfor %}
        </header>
        <section class="box alt special">
            <div class="row uniform">
            {% for section in site.data.sections %}
                {% if section.name == 'spread-bytes' %}
                    {% for project in section.projects %}
                        <section class="4u 6u(medium) 12u$(xsmall)">
                            <span class="icon alt major {{project.icon}}"></span>
                            <h3>{{project.title}}</h3>
                            <p>{{project.description}}</p>
                            <ul class="actions">
                                <li>{{project.url}}</li>
                            </ul>
                        </section>
                    {% endfor %}        
                {% endif %}
            {% endfor %}
            </div>
        </section>
    </div>
</div>