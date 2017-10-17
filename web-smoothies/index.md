---
layout: default
---
<!-- Main -->
<div id="main" class="wrapper style1">
    <div class="container">
        {% for section in site.data.sections %}
            {% if section.name == 'web-smoothies' %}
                <header class="major major-{{section.color}}">      
            {% endif %}
        {% endfor %}
            {% for section in site.data.sections %}
                {% if section.name == 'web-smoothies' %}
                    <h2>Welcome to {{ section.title }}</h2>
                    {% for info in section.infos %}
                        <p>{{ info }}</p>
                    {% endfor %}        
                {% endif %}
            {% endfor %}
        </header>
    </div>
</div>
<!-- Content -->
{% if site.posts.size == 0 %}
<section id="five" class="wrapper style2 fade">
    <div class="container">
        <h3><a href="{{ post.url }}">Sorry...</a></h3>
        No content found...
    </div>
    <section class="special">
            <ul class="actions">
                <li><a href="" class="button">Home</a></li>
            </ul>
    </section>
</section>
{% else %}
{% for post in site.posts %}
<!-- Five -->
<section id="five" class="wrapper {% cycle 'style2', 'style1' %} fade">
    <div class="container">
        <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
        {{ post.excerpt }}
        {% if post.meetup %} <p>When: {{post.when  | date: "%b %-d, %Y" }} from {{ post.from }} to {{ post.to }}</p> {% endif %}
        {% if post.meetup %} <p>Where: {{post.where}}</p> {% endif %}
        {% if post.meetup %} <p>Meetup RSVP: {{post.meetup}}</p> {% endif %}
    </div>
    <section class="special">
            <ul class="actions">
                <li><a href="{{ post.event-url }}" class="button">Read more</a></li>
            </ul>
    </section>
</section>
{% endfor %}
{% endif %}

