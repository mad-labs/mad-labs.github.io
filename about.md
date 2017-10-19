---
layout: default
---

<div id="main" class="wrapper style1">
    <div class="container">
        <header class="major">
            <h2>About</h2>
            <p></p>
        </header>
        <!-- Content -->
		<section id="content">
			<h3>From an idea of {{ site.data.about.whoami.name }}</h3>
			{% for resume_row in site.data.about.whoami.resume %}
				<p>{{ resume_row }}</p>
			{% endfor %}
			<ul>
				{% for contact in site.data.about.whoami.contacts %}
					<li>{{contact.name}} <a href="{{contact.url}}">{{contact.link_txt}}</a></li>
				{% endfor %}
            </ul>
            {% for link in site.data.about.links %}
				<h3>{{link.title}}</h3>
				<p>{{link.description}}</p>
				<ul>
				{% for item in link.list %}
					<li><a href="{{item.url}}">{{item.name}}</a></li>
				{% endfor %}
				</ul>
			{% endfor %}
		</section>
    </div>
</div>
