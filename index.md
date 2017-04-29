---
layout: default
---

<!-- Banner -->
<section id="banner">
    <div class="content">
        <header>
            <blockquote><p>It... Could... Woork!!!!</p></blockquote>
            <span class="image"><img src="{{ site.url }}{{ site.baseurl }}/{{site.imgs}}/pic01.jpg" alt="" /></span>
            <h1 class="hero"><strong class="hg-yellow">Mad Labs</strong></h1>
        </header>
    </div>
    <a href="#one" class="goto-next scrolly">Next</a>
</section>

<!-- One -->
<section id="one" class="spotlight madlabs bottom">
    <span class="image fit main"><img src="{{ site.url }}{{ site.baseurl }}/{{site.imgs}}/pic02.jpg" alt="" /></span>
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
{% include sections.html %}
{% endfor %}

<!-- Five -->
<section id="five" class="wrapper spreadbytes special fade-up">
    <div class="container">
        <header class="major">
            <h2>Mad Labs - Spred Bytes</h2>
            <p>Open source projects</p>
        </header>
        <div class="box alt">
            <div class="row uniform">
                <section class="4u 6u(medium) 12u$(xsmall)">
                    <span class="icon alt major fa-files-o"></span>
                    <h3>sb-jekyll-revealjs</h3>
                    <p>A Jekyll-based framework for creating simle presentations with Reveal.js and markdown.</p>
                    <ul class="actions">
                        <li><a href="https://github.com/mad-labs/sb-jekyll-revealjs" class="button">Go to project</a></li>
                    </ul>
                </section>
                <section class="4u 6u$(medium) 12u$(xsmall)">
                    <span class="icon alt major fa-comment"></span>
                    <h3>Coming soon..</h3>
                    <p>Stay tuned for the news!</p>
                    <ul class="actions">
                        <li><a href="{{ site.url }}{{ site.baseurl }}/" class="button">Learn More</a></li>
                    </ul>
                </section>
                <section class="4u$ 6u(medium) 12u$(xsmall)">
                    <span class="icon alt major fa-flask"></span>
                    <h3>Coming soon..</h3>
                    <p>Stay tuned for the news!</p>
                    <ul class="actions">
                        <li><a href="{{ site.url }}{{ site.baseurl }}/" class="button">Learn More</a></li>
                    </ul>
                </section>
                <!--
                <section class="4u 6u$(medium) 12u$(xsmall)">
                    <span class="icon alt major fa-paper-plane"></span>
                    <h3>Coming soon..</h3>
                    <p>Stay tuned for the news!</p>
                </section>
                <section class="4u 6u(medium) 12u$(xsmall)">
                    <span class="icon alt major fa-file"></span>
                    <h3>Coming soon..</h3>
                    <p>Stay tuned for the news!</p>
                </section>
                <section class="4u$ 6u$(medium) 12u$(xsmall)">
                    <span class="icon alt major fa-lock"></span>
                    <h3>Coming soon..</h3>
                    <p>Stay tuned for the news!</p>
                </section>
                -->
            </div>
        </div>
        <!--
        <footer class="major">
            <ul class="actions">
                <li><a href="{{ site.url }}{{ site.baseurl }}/" class="button">Learn More</a></li>
            </ul>
        </footer>
        -->
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
        <!--
        <form method="post" action="#" class="container 50%">
            <div class="row uniform 50%">
                <div class="8u 12u$(xsmall)"><input type="email" name="email" id="email" placeholder="Your Email Address" /></div>
                <div class="4u$ 12u$(xsmall)"><input type="submit" value="Get Started" class="fit special" /></div>
            </div>
        </form>
        -->
    </div>
</section>
