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
			<!-- <a href="{{ site.url }}{{ site.baseurl }}/#" class="image fit"><img src="{{ site.url }}{{ site.baseurl }}/{{ site.images }}/pic07.jpg" alt="" /></a> -->
			<h3>From an idea of {{ site.data.about.whoami.name }}</h3>
			{% for resume_row in site.data.about.whoami.resume %}
				<p>{{ resume_row }}</p>
			{% endfor %}
			<ul>
				{% for contact in site.data.about.whoami.contacts %}
					<li>{{contact.name}} <a href="{{contact.url}}">{{contact.link_txt}}</a></li>
				{% endfor %}
            </ul>
			<h3>Thanks and attributions</h3>
			<p>Thanks to ours sponsors:</p>
			<ul>
            {% for sponsor in site.data.about.sponsors %}
                <li><a href="{{sponsor.url}}">{{sponsor.name}}</a></li>
            {% endfor %}
			</ul>
            <p>Website design:</p>
   			<p>Thanks for website design:</p>
			<ul>
				<li><a href="https://html5up.net/">https://html5up.net/</a></li>
			</ul>
            <p>Images:</p>
   			<p>Thanks for images to:</p>
			<ul>
                <li><a href="http://clipart-library.com/">http://clipart-library.com/</a></li>
				<li><a href="http://www.psdgraphics.com/">http://www.psdgraphics.com/</a></li>
			</ul>
            <p>Liceses:</p>
			<ul>
                <li><a href="https://creativecommons.org/licenses/by/3.0/">https://creativecommons.org/licenses/by/3.0/</a></li>
				<li><a href="https://opensource.org/licenses/MIT">https://opensource.org/licenses/MIT</a></li>
			</ul>
		</section>
    </div>
</div>
