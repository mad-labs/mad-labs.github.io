---
title: Introduction to Jekyll
description: Introduction to Jekyll - a static site generator

databackgroundimage: /assets/images/grunge-danger_custom_2.jpg
#databackgroundsize: "100px" 
#databackgroundposition: "center"
#databackgroundrepeat: "repeat"

#databackgroundcolor: "#ff0000"

#databackgroundiframe: ""

#databackgroundvideo: "https://s3.amazonaws.com/static.slid.es/site/homepage/v1/homepage-video-editor.mp4,https://s3.amazonaws.com/static.slid.es/site/homepage/v1/homepage-video-editor.webm" 
#databackgroundvideoloop: true
#databackgroundvideomuted: true

theme: night
reveal:
  transition: concave

intros:
  - presentation/intro_web-smoothies.md
  - presentation/intro_madlabs.md
  - presentation/intro_whoami.md

outros:
  - presentation/outro_contacts.md
  
whoami:
  name: Gabriele Manfredi
  image:
    title: Gabriele
    url: /assets/images/fb_profile.jpg
  contacts:
    - "Skype: [gabriele_manfredi](skype:gabriele_manfredi?add)"
    - "Twitter: [GabOnlain](https://twitter.com/GabOnlain)"
    - "Facebook:  [Gabriele Manfredi](https://www.facebook.com/Gabriele.Manfredi.999/)"
    - "Mail: [gabriele.manfredi.999@gmail.com](mailto:gabriele.manfredi.999@gmail.com)"
  resume:
    - "Senior Java Developer in Object Method: [http://www.objectmethod.it/](http://www.objectmethod.it/)"
    - "Strong Web development skills: Java (SE -EE), SQL, Html, JavaScript, CSS and more..."
    - "Worked with Reply, NTT, Enel, Eni and more..."
    - "Love develop, boardgame, books, series, movie, photography & learn new things"
---

![Jekyll Log](https://jekyllrb.com/img/logo-2x.png "Jekyll Logo")

# A simple static site generator
<!-- next-slide -->

## So what is Jekyll, exactly?

**Jekyll is a simple**, blog-aware, **static site generator**. **It takes a template directory** containing raw
text files in various formats, runs it through a converter 
(like [Markdown](https://daringfireball.net/projects/markdown)) and our 
[Liquid](https://github.com/Shopify/liquid/wiki) renderer, 
**and spits out a complete, ready-to-publish static website** suitable for serving with your favorite web server.

**Jekyll also happens to be the engine behind** [GitHub Pages](https://pages.github.com/), 
which means you can use Jekyll to host your project’s page, blog, or website from GitHub’s servers for free.
<!-- vertical-slide -->

### Why use a static site generator?

* **Simple**: No other configuration than static website hosting.

* **Secure**: No database to hack. No latency due to using HTTPS

* **Great Performance**: Pages are just HTML. No database calls, no complex layers of caching needed.

* **Cheap**: Hosting is free or cheap and costs don't increase with load. Can use a CDN (see performance).

* **Allows for complexity**: Do anything you want on a page because queries aren't being executed at load time.

* **Efficient**: Minimal infrastructure to manage. Easy to start a project, or create a feature branch and throw it on a staging server. 
<!-- vertical-slide -->

### Competitor

![https://www.staticgen.com/]({{ "assets/images/top_open_source_static_site_generators.png" }})
<!-- next-slide -->

### Installation

Getting Jekyll installed and ready-to-go should only take a few minutes.

Installing Jekyll is easy and straight-forward, but there are a few requirements you’ll need to make sure your system has before you start:

* Ruby

* RubyGems
<!-- vertical-slide -->

### Ruby

![Ruby Logo](https://www.ruby-lang.org/{{ site.images }}/header-ruby-logo.png "Ruby Logo")

### Debian or Ubuntu

Debian GNU/Linux and Ubuntu use the apt package manager. You can use it like this:

```sh
$ sudo apt-get install ruby-full
```

### Windows

If you are on Windows, there is a great project to help you install Ruby: 

RubyInstaller: [https://rubyinstaller.org/](https://rubyinstaller.org/)
<!-- vertical-slide -->

### RubyGems

![Ruby Gems Logo](https://rubygems.org/favicon.ico "Ruby Gems Logo")

* Download from [https://rubygems.org/pages/download](https://rubygems.org/pages/download)

* Unpack into a directory and cd there

* Install (you may need admin/root privilege)

```sh
ruby setup.rb
```
<!-- next-slide -->

#### Basic Usage

The Jekyll gem makes a jekyll executable available to you in your Terminal window. You can use this command in a number of ways:

```sh
#Install Jekyll and Bundler gems through RubyGems
~ $ gem install jekyll bundler

#Create a new Jekyll site at ./myblog
~ $ jekyll new myblog

#Change into your new directory
~ $ cd myblog

#Build the site on the preview server
~/myblog $ bundle exec jekyll serve

#Now browse to http://localhost:4000
```
<!-- vertical-slide -->

### Basic concepts and commands

Jekyll will use these files and folders as a basis to create a fully static website. 

This static website is generated in the **_site** folder by default.

Jekyll will process all files with a **YAML Front Matter** (including empty YAML Front Matters), 
make them available in memory and make them usable by the Liquid templating engine and Jekyll tags.

Files and folders with a name starting with underscore will not be transferred to the _site folder, 
while the others will be after having been processed by the Jekyll pipeline.

When in your project folder, the jekyll **build** or **bundle exec jekyll build** commands are used to 
generate your website. 

If you want the regeneration to happen every time a file is changed, just 
use the --watch flag: jekyll build --watch.


<!-- vertical-slide -->

#Jekyll also comes with a built-in development server that will allow you to preview what the generated site will look like in your browser locally.

```sh
$ jekyll serve
#=> A development server will run at http://localhost:4000/
#Auto-regeneration: enabled. Use `--no-watch` to disable.

$ jekyll serve --detach
#=> Same as `jekyll serve` but will detach from the current terminal.
#If you need to kill the server, you can `kill -9 1234` where "1234" is the PID.
#If you cannot find the PID, then do, `ps aux | grep jekyll` and kill the instance.
```

<!-- next-slide -->

### Directory structure

Jekyll is, at its core, a text transformation engine. The concept behind the system is this: you give it text written in your favorite markup language, be that Markdown, Textile, or just plain HTML, and it churns that through a layout or a series of layout files.

<!-- vertical-slide -->

#### A basic Jekyll site usually looks something like this:

```sh
index.html
_config.yml
_data /
  members.yml
_drafts /
  on-simplicity-in-technology.md
_includes /
  footer.html
  header.html
_layouts /
  default.html
_posts /
  2009-04-26-barcamp-boston-4-roundup.md
_sass /
  _layout.scss
_site /
```

<!-- vertical-slide -->

#FILE | DIRECTORY	DESCRIPTION
------------ | ------------
\_config.yml | Stores configuration data. Many of these options can be specified from the command line executable but it’s easier to specify them here so you don’t have to remember them.
\_data | Well-formatted site data should be placed here. The Jekyll engine will autoload all data files (using either the .yml,  .yaml, .json or .csv formats and extensions) in this directory, and they will be accessible via `site.data`. If there's a file members.yml under the directory, then you can access contents of the file through site.data.members.
\_includes | These are the partials that can be mixed and matched by your layouts and posts to facilitate reuse. The liquid tag {% raw %}`{% include file.ext %}`{% endraw %} can be used to include the partial in \_includes/file.ext.
\_layouts | These are the templates that wrap posts. Layouts are chosen on a post-by-post basis in the YAML Front Matter, which is described in the next section. The liquid tag {% raw %}`{{ content }}`{% endraw %} is used to inject content into the web page.
\_posts | Your dynamic content, so to speak. The naming convention of these files is important, and must follow the format: YEAR-MONTH-DAY-title.MARKUP. The permalinks can be customized for each post, but the date and markup language are determined solely by the file name.

<!-- vertical-slide -->

#FILE | DIRECTORY	DESCRIPTION
------------ | ------------
\_sass | These are sass partials that can be imported into your main.scss which will then be processed into a single stylesheet main.css that defines the styles to be used by your site.
\_site | This is where the generated site will be placed (by default) once Jekyll is done transforming it. It’s probably a good idea to add this to your .gitignore file.
index.html | Provided that the file has a YAML Front Matter section, it will be transformed by Jekyll. The same will happen for any .html, .markdown, .md, or .textile file in your site’s root directory or directories not listed above.
Other Files/Folders | Every other directory and file except for those listed above — such as css and images folders, favicon.ico files, and so forth — will be copied verbatim to the generated site. There are plenty of sites already using Jekyll if you’re curious to see how they’re laid out.

<!-- next-slide -->

### Front Matter

The front matter is where Jekyll starts to get really cool. Any file that contains a YAML front matter block will be processed by Jekyll as a special file. The front matter must be the first thing in the file and must take the form of valid YAML set between triple-dashed lines.

```yaml
---
layout: post
title: Blogging Like a Hacker
---
```

Between these triple-dashed lines, you can set predefined variables or even create custom ones of your own.

These variables will then be available to you to access using Liquid tags both further down in the file and also in any layouts or includes that the page or post in question relies on.

<!-- next-slide -->

### Templates

Jekyll uses the Liquid templating language to process templates. All of the standard [Liquid](https://shopify.github.io/liquid/) tags and filters are supported.

![Liquid website]({{ "assets/images/liquid_template_language.png" }})

Jekyll even adds a few handy filters and tags of its own to make common tasks easier.
<!-- vertical-slide -->

### Liquid tags

There are two main types of tags in Liquid:

* Output tags {% raw %}**{{ output }}**{% endraw %} allowing you to output variables in your templates.
{% raw %}
```liquid
<li>{{ item.title }}</li>
```
{% endraw %}
* Logical or execution tags {% raw %}**{% logic %}**{% endraw %}. For example {% raw %}**{% if %}**{% endraw %},
  {% raw %}**{% endif %}**{% endraw %} or {% raw %}**{% assign myariable = site.mycollection %}**{% endraw %}
  all allow you execute actions or add logic to your templates.

{% raw %}
```liquid
{% assign blogpostsPerTitle = site.posts | sort: 'title' | reverse %}
```
```liquid
{% if user.age > 18 %}
  <p>Would you like a beer ?</p>
{% endif %}
```
```liquid
{% for item in site.posts %}
  {{ item.title }}
{% endfor %}
```
{% endraw %}
<!-- vertical-slide -->

### Access your data

When it runs, Jekyll makes a bunch of variables available to you via the Liquid templating system.

* **site**: Sitewide information + configuration settings from  _config.yml.

* **page**: Page specific information + the YAML front matter. Custom variables set via the YAML 
  Front Matter will be available here. See below for details.

* **paginator**: When the paginate configuration option is set, this variable becomes available for use.
  See Pagination for details.

* **layout**: Layout specific information + the YAML front matter. Custom variables set via the YAML
  Front Matter in layouts will be available here.

* **content**: In layout files, the rendered content of the Post or Page being wrapped. Not defined in Post
  or Page files.

Ex.
{% raw %}
```liquid
{{ site.pages }} <!--A list of all Pages.-->
{{ page.url }} <!--The URL of the Post without the domain.-->
{{ paginator.total_posts }} <!--Total number of Posts.-->
```
{% endraw %}

<!-- vertical-slide -->


### e.g. Displaying an index of posts

With templates you can create an index of posts on another page, thanks to the Liquid template language and its tags:

{% raw %}
```liquid
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
```
{% endraw %}

<!-- vertical-slide -->

### Includes

If you have small page fragments that you wish to include in multiple places on your site, you can use the include tag.

{% raw %}
```liquid
{% include footer.html %}
```
{% endraw %}

Jekyll expects all include files to be placed in an \_includes directory at the root of your source directory.
This will embed the contents of <source>/\_includes/footer.html into the calling file.

You can also pass parameters to an include. Omit the quotation marks to send a variable’s value. Liquid curly brackets should not be used here:

{% raw %}
```liquid
{% include footer.html param="value" variable-param=page.variable %}
```
{% endraw %}

These parameters are available via Liquid in the include:

{% raw %}
```liquid
{{ include.param }}
```
{% endraw %}

<!-- vertical-slide -->

### Including files relative to another file

You can also choose to include file fragments relative to the current file:

{% raw %}
```liquid
{% include_relative somedir/footer.html %}
```
{% endraw %}

You won’t need to place your included content within the \_includes directory.
Instead, the inclusion is specifically relative to the file where the tag is being used.
For example, if \_posts/2014-09-03-my-file.markdown uses the include_relative tag, the included file must be within the \_posts directory, or one of its subdirectories.
You cannot include files in other locations.

All the other capabilities of the include tag are available to the include_relative tag, such as using variables.

<!-- vertical-slide -->

### Link

If you want to include a link to a collection’s document, a post, a page or a file the link tag will generate the correct permalink URL for the path you specify.

You must include the file extension when using the link tag.

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

If you would like to include a link to a post on your site, the post_url tag will generate the correct permalink URL for the post you specify.

{% raw %}
```liquid
{{ site.baseurl }}{% post_url 2010-07-21-name-of-post %}
```
{% endraw %}

If you organize your posts in subdirectories, you need to include subdirectory path to the post:

{% raw %}
```liquid
{{ site.baseurl }}{% post_url /subdir/2010-07-21-name-of-post %}
```
{% endraw %}

There is no need to include the file extension when using the post_url tag.
<!-- vertical-slide -->

### Including images and resources

Chances are, at some point, you’ll want to include images, downloads, or other digital assets along with your text content.

One common solution is to create a folder in the root of the project directory called something like assets or downloads, into which any images, downloads or other resources are placed.

Including an image asset in a post:

```markdown
... which is shown in the screenshot below:
![My helpful screenshot]({{ site.url }}/{{ site.assets }}/screenshot.jpg)
```
<!-- next-slide -->

### Writing posts

One of Jekyll’s best aspects is that it is “blog aware”.

If you write articles and publish them online, you can publish and maintain a blog simply by managing a folder of text-files on your computer.
<!-- vertical-slide -->

### The Posts Folder

As explained on the directory structure page, the \_posts folder is where your blog posts will live. These files are generally Markdown or HTML, but can be other formats with the proper converter installed. All posts must have YAML Front Matter, and they will be converted from their source format into an HTML page that is part of your static site.
<!-- vertical-slide -->

### Creating Post Files

To create a new post, all you need to do is create a file in the \_posts directory. How you name files in this folder is important. Jekyll requires blog post files to be named according to the following format:

```sh
.
..
YEAR-MONTH-DAY-title.MARKUP
```

Where YEAR is a four-digit number, MONTH and DAY are both two-digit numbers, and MARKUP is the file extension representing the format used in the file. For example, the following are examples of valid post filenames:

```sh
.
..
2011-12-31-new-years-eve-is-awesome.md
2012-09-12-how-to-write-a-blog.md
```
<!-- next-slide -->

### Creating pages

In addition to writing posts, another thing you may want to do with your Jekyll site is create static pages. By taking advantage of the way Jekyll copies files and directories, this is easy to do.

There are two main ways of creating pages:

* Place named HTML or Markdown files for each page in your site’s root folder.

* Create a folder in the site’s root for each page, and place an index.html or index.md file in each page folder.

Both methods work fine (and can be used in conjunction with each other), with the only real difference being the resulting URLs.
<!-- next-slide -->

### Collections

Not everything is a post or a page. Collections allow you to define a new type of document that behave like Pages or Posts do normally, but also have their own unique properties and namespace.
<!-- vertical-slide -->

### Using Collections - Step 1

Tell Jekyll to read in your collection, adding the following to your site’s 

```sh
_config.yml
```

replacing my_collection with the name of your collection:

```yaml
collections:
- my_collection
```

You can optionally specify metadata for your collection in the configuration:

```yaml
collections:
  my_collection:
    foo: bar
```
<!-- vertical-slide -->

### Using Collections - Step 2

Create a corresponding folder 

```sh
_my_collection /
```

and add documents. 

YAML Front Matter is read in as data if it exists, and everything after it is stuck in the Document’s content attribute. If no YAML Front Matter is provided, Jekyll will not generate the file in your collection.

Be sure to name your directories correctly: *the folder* must be named *identically* to the collection you defined in your \_config.yml file, with the addition of the preceding _ character.
<!-- next-slide -->

### Assets

Jekyll provides built-in support for Sass and can work with CoffeeScript via a Ruby gem. In order to use them, you must first create a file with the proper extension name (one of .sass, .scss, or .coffee) and start the file with two lines of triple dashes, like this:

```sh
---
---

// start content
.my-definition
  font-size: 1.2em
```

Jekyll treats these files the same as a regular page, in that the output file will be placed in the same directory that it came from. For instance, if you have a file named css/styles.scss in your site’s source folder, Jekyll will process it and put it in your site’s destination folder under css/styles.css
<!-- next-slide -->

### Themes

Jekyll has an extensive theme system, which allows you to leverage community-maintained templates and styles to customize your site’s presentation.

Jekyll themes package layouts, includes, and stylesheets in a way that can be overridden by your site’s content.
<!-- vertical-slide -->

### Installing a theme

To install a theme

* add the theme to your site’s Gemfile:
```sh
 gem 'my-awesome-jekyll-theme'
```
* Save the changes to your Gemfile
* Run the command bundle install to install the theme
* Finally, activate the theme by adding the following to your site’s \_config.yml:

```yaml
 theme: my-awesome-jekyll-theme
```
<!-- vertical-slide -->

### Overriding theme defaults

Jekyll themes set default layouts, includes, and stylesheets, that can be overridden by your site’s content.

For example, if your selected theme has a page layout, you can override the theme’s layout by creating your own page layout in the \_layouts folder (e.g., \_layouts/page.html).

Jekyll will look first to your site’s content, before looking to the theme’s defaults, for any requested file in the following folders:
```sh
/assets
/_layouts
/_includes
/_sass
```

<!-- next-slide -->

### Jekyll and Github pages

Jekyll is the engine powering Github Pages, a tool allowing you to manage and host Jekyll site for free.
All Github repositories allow you to use Jekyll. The setup is a little bit différent for projects than for 
users or organisations but it remains quite simple.

By combining Jekyll and Github pages, you will get yourself a collaborative environment, free hosting and 
a website fully managed with Git.

[https://pages.github.com/](https://pages.github.com/)


<!-- next-slide -->

### Jekyll website

All this information and more are available in official [Jekyll](https://jekyllrb.com/) website

![Jekyll website]({{ "assets/images/jekyll-website.png" }})

<!-- next-slide -->

### Jekyll resources

 * Jekyll official site: [https://jekyllrb.com/](https://jekyllrb.com/)
 
 * Liquid documentation: [http://shopify.github.io/liquid/](http://shopify.github.io/liquid/)
 
 * Jekyll cheat sheet: [http://jekyll.tips/jekyll-cheat-sheet/](http://jekyll.tips/jekyll-cheat-sheet/)
 
 * GitHub pages docs: [https://pages.github.com/](https://pages.github.com/)

 <!-- next-slide -->

