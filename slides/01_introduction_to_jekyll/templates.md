
### Layouts and Templates

Jekyll uses the [Liquid](https://shopify.github.io/liquid/) templating language to process layouts

![Liquid website]({{ "assets/images/liquid_template_language.png" }})

It's been created by Shopify and written in Ruby.

Jekyll supports all its tag and filter and also adds a few to make common tasks easier.

<!-- vertical-slide -->

### Liquid tags

There are tree main elements in Liquid:

* Tags
{% raw %}
```liquid
{% if user.name == 'elvis' %}
  Hey Elvis
{% endif %}
```
{% endraw %}

Tags make up the programming logic that tells templates what to do

* Objects
{% raw %}
```liquid
{{ product.title }} <!-- Output: Awesome T-Shirt-->
```
{% endraw %}

Objects contain attributes that are used to display "dynamic" content on a page

* Filters
{% raw %}
```liquid
{{ 'sales' | append: '.jpg' }} <!-- Output: sales.jpg -->
```
{% endraw %}

Filters are used to modify the output of strings, numbers, variables, and objects.

<!-- vertical-slide -->

e.g.

{% raw %}
```liquid
<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <span class="post-meta">
        {{ post.date | date: "%b %-d, %Y" }}
      </span>
      <h2>
        <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a> 
      </h2>
    </li>
  {% endfor %}
</ul>
{{ content }}
{% if site.disqus.shortname %}
  {% include disqus_comments.html %}
{% endif %}
```
{% endraw %}

<!-- vertical-slide -->

### Access your data

Inside your layout you can access to some data, available inside predefined variables:

* **site**: sitewide information + configuration settings from  _config.yml

* **page**: page specific information + the YAML front matter

* **layout**: layout specific information

* **content**: in layout files, the rendered content of the post or the page

* **paginator**: when the paginate configuration option is set, this variable becomes available for use

<!-- vertical-slide -->

### Includes

There are small page fragments to include in multiple places on your site

{% raw %}
```liquid
{% include footer.html %}
```
{% endraw %}

Jekyll expects all include files to be placed in an **\_includes** directory

You can also pass parameters to an include.

{% raw %}
```liquid
{% include footer.html param="value" variable-param=page.variable %}
```
{% endraw %}

These parameters will be available via Liquid in the included template.

<!-- vertical-slide -->

### Including files relative to another file

You can also choose to include file fragments relative to the current file:

{% raw %}
```liquid
{% include_relative somedir/footer.html %}
```
{% endraw %}

In this way you won’t need to place your included content within the \_includes directory, but you cannot include files in other locations :(

<!-- vertical-slide -->

### Link

If you want to include a link to a collection’s document, a post, a page or a file the link tag will generate the correct permalink URL

Ex.
{% raw %}
```liquid

{{ site.baseurl }}{% link _collection/name-of-document.md %}

{{ site.baseurl }}{% link _posts/2016-07-26-name-of-post.md %}

{{ site.baseurl }}{% link news/index.html %}

{{ site.baseurl }}{% link /{{ site.assets }}/files/doc.pdf %}

```
{% endraw %}

<!-- vertical-slide -->

### Post URL

An also you can include a link to a post

{% raw %}
```liquid
{{ site.baseurl }}{% post_url 2010-07-21-name-of-post %}
```
{% endraw %}

There is no need to include the file extension when using the post_url tag.

<!-- vertical-slide -->

### Including images and resources

Chances are, at some point, you’ll want to include images, downloads, or other digital assets along with your text content.

One common solution is to create a folder in the root directory called like assets or similar...

Including an image like this:

{% raw %}
```liquid
... which is shown in the screenshot below:
![My helpful screenshot]({{ site.url }}/{{ site.assets }}/screenshot.jpg)
```
{% endraw %}

<!-- vertical-slide -->

### Example:

with this content: ```_post/2014-08-07-introduction-to-jekyll.md```

{% raw %}
```html
---
layout: post
category: talk
when: 2017-02-23
from: "19:00"
to: "22:00"
where: '<a href="http://www.opendotlab.it/">OpenDot</a>'
event-url: /slides/01_introduction_to_jekyll
---

<span class="image right">
      <img src="{{ site.baseurl }}/{{ site.images }}/mad_scientist.png" alt="">
</span>
Jekyll is a simple, blog-aware, static site generator. It takes a
template directory containing raw text files in various formatsvand
spits out a complete, ready-to-publish static website suitable for
serving with your favorite web server.
```
{% endraw %}

<!-- vertical-slide -->

and this layout: ```_layout/post.html```

{% raw %}
```html
<!DOCTYPE HTML>
<html>
    
    {% include head.html %}

    <body class="landing">
        <div id="page-wrapper">

            {% include header.html %}

            {{ content }}
            
            {% include footer.html %}

        </div>
    </body>
</html>
```
{% endraw %}

<!-- vertical-slide -->

Jekyll will generate this page:

![Post Example]({{ "assets/images/post_example.png" }})

<!-- next-slide -->