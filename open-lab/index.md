---
layout: default
---
<!-- Main -->
<div id="main" class="wrapper style1">
    <div class="container">
        {% for section in site.data.sections %}
            {% if section.name == 'open-lab' %}
                <header class="major major-{{section.color}}">      
            {% endif %}
        {% endfor %}
            {% for section in site.data.sections %}
                {% if section.name == 'open-lab' %}
                    <h2>Welcome to {{ section.title }}</h2>
                    {% for info in section.infos %}
                        <p>{{ info }}</p>
                    {% endfor %}        
                {% endif %}
            {% endfor %}
        </header>
    </div>
</div>