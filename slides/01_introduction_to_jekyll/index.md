---
title: Introduction to Jekyll
description: Introduction to Jekyll - a static site generator
layout: presentation_multipage
databackgroundimage: /src/assets/images/grunge-danger_custom_2.jpg

theme: night

reveal:
  transition: concave

intros:
  - presentation/intro_web_smoothies.md
  - presentation/intro_madlabs.md
  - presentation/intro_whoami.md

outros:
  - presentation/outro_contacts.md

whoami:
  name: Gabriele Manfredi
  image:
    title: Gabriele
    url: /src/assets/images/fb_profile.jpg
  contacts:
    - "Skype: [gabriele_manfredi](skype:gabriele_manfredi?add)"
    - "Twitter: [GabOnlain](https://twitter.com/GabOnlain)"
    - "Facebook:  [Gabriele Manfredi](https://www.facebook.com/Gabriele.Manfredi.999/)"
    - "Mail: [gabriele.manfredi.999@gmail.com](mailto:gabriele.manfredi.999@gmail.com)"
  resume:
    - "Java Developer in Object Method: [http://www.objectmethod.it/](http://www.objectmethod.it/)"
    - "Work maily with: Java (SE -EE), SQL, Html, JavaScript, CSS and more..."
    - "Love to develop, play boardgames, attend theatre classes, try to take photos & learning new things"

slides:
  - title.md
  - so_what_is_Jekyll_exactly.md
  - installation.md
  - getting_started.md
  - how_it_works.md
  - directory_structure.md
  - templates.md
  - writing_contents.md
  - themes.md
  - advanced_uses.md
  - jekyll_and_github_pages.md
  - jekyll_resources.md
---

{% for slide in page.slides %}
  {% include_relative {{ slide }} %}
{% endfor %}

