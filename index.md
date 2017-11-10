---
layout: default
---

<!-- Banner -->
<section id="banner">
    <div class="content">
        <header>
            <blockquote><p>It... Could... Woork!!!!</p></blockquote>
            <span class="image_square"><img src="{{ site.url }}{{ site.baseurl }}/{{ site.images }}/pic01.png" alt="" /></span>
            <!-- <h1 class="hero"><strong class="hg-yellow">Mad Labs</strong></h1> -->
            <section class="special">
                <ul class="icons">
                    <li><a href="https://twitter.com/madlabsprojects" class="icon alt fa-twitter"><span class="label">Twitter</span></a></li>
                    <li><a href="https://www.facebook.com/madlabsprojects" class="icon alt fa-facebook"><span class="label">Facebook</span></a></li>
                    <li><a href="https://www.meetup.com/it-IT/MadLabs-Web-Development-a-Milano/" class="icon alt fa-meetup"><span class="label">Meetup</span></a></li>
                    <li><a href="{{ site.url }}/slack.html" class="icon alt fa-slack"><span class="label">Slack</span></a></li>
                    <li><a href="https://github.com/mad-labs/" class="icon alt fa-github"><span class="label">Github</span></a></li>
                    <li><a href="mailto:madlabsprojects@gmail.com" class="icon alt fa-envelope-o"><span class="label">Email</span></a></li>
                </ul>
            </section>
        </header>
    </div>
    <a href="#one" class="goto-next scrolly">Next</a>
</section>
<!-- One -->
<section id="one" class="spotlight madlabs bottom">
    <span class="image fit main"><img src="{{ site.url }}{{ site.baseurl }}/{{ site.images }}/pic02.jpg" alt="" /></span>
    <div class="content">
        <div class="container">
            <div class="row">
                <div class="4u 12u$(medium)">
                    <header>
                        <h2>What's <strong class="hg-yellow">Mad Labs</strong>?</h2>
                        <p>The Mad Labs organization is a community of crazy technologists 
                           working on experiments designed to push
                           our software development skills into 
                           <strong class="hg-yellow">new spaces</strong>.
                        </p>
                    </header>
                </div>
                <div class="4u 12u$(medium)">
                    <p>Our projects provides an open, collaborative 
                       environment for interdisciplinary exploration 
                       and debate. <strong class="hg-yellow">We are students,
                       colleagues and professors in the same time</strong>:
                       learning together and from one another.
                    </p>
                </div>
                <div class="4u$ 12u$(medium)">
                    <p>We like to discuss our work, to network, and to 
                       <strong class="hg-yellow">develop ideas that will 
                       improve ourself</strong> through exploration and 
                       experimentation. Below you'll find all our projects.
                    </p>
                </div>
            </div>
        </div>
    </div>
    <a href="#two" class="goto-next scrolly">Next</a>
</section>

{% for section in site.data.sections %}
{% if section.homepage %}
{% include sections.html %}
{% endif %}
{% endfor %}

<!-- Five -->
<section id="five" class="wrapper spreadbytes special fade-up">
    <div class="container">
        <header class="major">
            {% for section in site.data.sections %}
                {% if section.name == 'spread-bytes' %}
                    <h2>{{ section.title }}</h2>
                    {% for info in section.infos %}
                        <p>{{ info }}</p>
                    {% endfor %}        
                {% endif %}
            {% endfor %}
        </header>
        <div class="box alt">
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
        </div>
    </div>
    <a href="#six" class="goto-next scrolly">Next</a>
</section>

<!-- Six -->
<section id="six" class="wrapper style2 special fade">
    <div class="container">
        <header>
            <h2>Keep in touch</h2>
            <p>Follow our channels for all news!</p>
        </header>
    </div>
</section>
