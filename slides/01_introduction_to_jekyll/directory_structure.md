
### Directory structure

Jekyll use pre-defined files and folder to generate our site.

After a **jekyll new** command, you will find this in your project foilder:

```sh
├── about.md
├── _config.yml
├── Gemfile
├── Gemfile.lock
├── index.md
└── _posts
    └── 2017-02-22-welcome-to-jekyll.markdown
...
```

And thats, thanks to Jekyll themes support, it enough to start generating our site

<!-- vertical-slide -->

Actually, a tipical Jekyll projects, also need other directories:

```sh
...
├── assets
│   └── main.scss
├── _includes
│   ├── footer.html
│   ├── header.html
│   └── head.html
├── _layouts
│   ├── default.html
│   ├── home.html
│   ├── page.html
│   └── post.html
└── _sass
    ├── minima
    │   ├── _base.scss
    │   └── _syntax-highlighting.scss
    └── minima.scss
```

<!-- vertical-slide -->

In details...

FILE | DESCRIPTION
------------ | ------------
\_config.yml | Is the main file, it stores **configuration data** in YAML format
index.md | simple text file, representing a "page": thanks to its **YAML Front Matter** will be transformed by Jekyll in html
about.md | same as before
Gemfile | this files contains all current gems installed for this jekyll project, usually we don't need to modify it

<!-- vertical-slide -->

FOLDER | DESCRIPTION
------------ | ------------
\_includes/ | these folder contains the html fragments be mixed and matched by your layouts
\_layouts/ | here there are the templates that wrap and style posts and pages
\_posts/ | the "dynamic" content, so to speak. Simple text file tranformed by Jekyll in a collection of posts.
\_data/ | well-formatted data file that Jekyll engine will autoload and make available via `site.data` variable
\_sass/ | sass partials that will be processed into a single stylesheet main.css
\_site/ | by default the generated site folder

<!-- vertical-slide -->


### YAML: YAML Ain't Markup Language

> YAML is a human friendly data serialization standard for all programming languages.

```yaml
invoice: 34843
date   : 2001-01-23
    address:
        lines: |
            458 Walkman 
            Dr. Suite #292
        city    : Royal Oak
product:
    - item        : &idBL394D
      price       : 450.00
    - item        : &idBL4438H
      price       : 2392.00
comments: >
    Late afternoon is best.

```

YAML: structure through indentation (one or more spaces), sequence denoted by dashes, and key value pairs separated by a colon. More at [offical site](http://www.yaml.org/)

<!-- vertical-slide -->

### Front Matter ?!?

The front matter is where Jekyll starts to get really cool.

Any file that contains a **YAML front matter block** :

```yaml
---
layout: post
title: Blogging Like a Hacker
---
```

will be processed by Jekyll as a **special file**.

* The front matter must be **the first thing** in the file
* must be **valid YAML**
* must be wrapped between **triple-dashed lines**

You can use space to set **predefined variables** or even **create custom ones**, that will be available to our **Liquid tags**

In that file and also in any **layouts** or **includes** that it relies on

<!-- vertical-slide -->

e.g. ```_config.yml```

{% raw %}
```yaml
title: Your awesome title
email: your-email@domain.com
description: > # this means to ignore newlines until "baseurl:"
  Write an awesome description for your new site here.
baseurl: "" # e.g. /blog
url: "" # e.g. http://example.com
twitter_username: jekyllrb
github_username:  jekyll

# Build settings
markdown: kramdown
theme: minima
gems:
  - jekyll-feed
exclude:
  - Gemfile
  - Gemfile.lock
```
{% endraw %}

<!-- vertical-slide -->

e.g. ```_layout/default.html```

{% raw %}
```liquid
<!DOCTYPE html>
<html lang="{{ page.lang | default: site.lang | default: "en" }}">
  {% include head.html %}
  <body>
    {% include header.html %}
    <main class="page-content" aria-label="Content">
      <div class="wrapper">
        {{ content }}
      </div>
    </main>
    {% include footer.html %}
  </body>
</html>
```
{% endraw %}

<!-- vertical-slide -->

e.g. ```_include/head.html```

{% raw %}
```liquid
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>{% if page.title %}{{ page.title | escape }}{% else %}{{ site.title | escape }}{% endif %}</title>
  <meta name="description" content="{{ page.excerpt | default: site.description | strip_html | normalize_whitespace | truncate: 160 | escape }}">

  <link rel="stylesheet" href="{{ "/{{ site.assets }}/main.css" | relative_url }}">
  <link rel="canonical" href="{{ page.url | replace:'index.html','' | absolute_url }}">
  <link rel="alternate" type="application/rss+xml" title="{{ site.title | escape }}" href="{{ "/feed.xml" | relative_url }}">
  
  {% if jekyll.environment == 'production' and site.google_analytics %}
  {% include google-analytics.html %}
  {% endif %}
</head>

```
{% endraw %}

<!-- vertical-slide -->

e.g. ```about.html```

{% raw %}
```liquid
---
layout: page
title: About
permalink: /about/
---

This is the base Jekyll theme. You can find out more
info about customizing your Jekyll theme
at [jekyllrb.com](https://jekyllrb.com/)

You can find the source code for the Jekyll new theme at:
{% include icon-github.html username="jekyll" %} /
[minima](https://github.com/jekyll/minima)

You can find the source code for Jekyll at
{% include icon-github.html username="jekyll" %} /
[jekyll](https://github.com/jekyll/jekyll)
```
{% endraw %}

<!-- next-slide -->