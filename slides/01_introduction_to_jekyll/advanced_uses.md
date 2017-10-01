
## Advanced Use

Here will follow some advance functionality of jekyll

<!-- vertical-slide -->

### Sass & CoffeeSctipt

Jekyll, out of the box, support compilation of Sass and CoffeeScript files.

To use it, you must create a file with proper extension (.sass, .scss, or .coffee) and start it with two lines of triple dashes:

```yaml
---
---

.my-definition
  font-size: 1.2em
```

Jekyll will process these files and put the output in the same directory that it came from.

For instance ```css/styles.scss``` will became ```_site/css/styles.css```

<!-- vertical-slide -->

### Front Matter defaults

Because people are lazy and is boring repeating a lot of configuration options Jekyll provides a way to set defaults in the site configuration.

It's enough using the defaults key in the **\_config.yml** file in your project’s root:

```yaml
defaults:
  -
    scope:
      path: "" # an empty string here means all files in the project
    values:
      layout: "simple"
```

In this way every content in the site will have the "simple" layout as default.

<!-- vertical-slide -->

### Data Files

In addition to the built-in variables, you can specify **your own custom data** that can be accessed via the **Liquid templating system**.

Putting in the **\_data** folder a file with **YAML**, **JSON**, or **CSV** extension, Jekyll will elaborate it and it content will be accessible via **site.data** variable

For example with a ```_data/author.yaml``` like this:

```yaml
- name: Bruce Wayne
  pic: buce.jpg

- name: Clark Kent
  pic: clark.jpg
```

you'll can access content with **site.data.authors** variable

{% raw %}
```liquid
{% for author in site.data.authors %}
  <li>
    <img src="{{ author.pics }}">
    <span>{{ author.name }}</span>
  </li>
{% endfor %}
```
{% endraw %}


<!-- vertical-slide -->

### Collections

A collections allow you to define a new type of **document** that behave like Pages or Posts.

To start using collections, follow these 3 steps:

* Step 1: Tell Jekyll to read in your collection
* Step 2: Add your content
* Step 3: Optionally render your collection’s documents into independent files

<!-- vertical-slide -->

### Step 1

Tell Jekyll to read in your collection, adding the following to your site’s 

```sh
_config.yml
```

at exmple to create a "slides" collection we need to insert in file something like:

```yaml
collections:
  slides
```

You can optionally specify **metadata** for your collection in the configuration:

```yaml
collections:
  slides:
    layout: presentation
    theme: night
```
<!-- vertical-slide -->

### Step 2

Add your content creating a corresponding folder, named **identically** to the defined collection __\_config.yml__ file "_" prefix 

```sh
...
│
├──── _slides/
│
...
```

and add documents.

Each collection will be accessible as a field on the site variable: for example, if you want to access the **slides** collection found in **\_slides**, you’d use **site.slides**.

YAML Front Matter is read in as data if it exists, and everything after it is stuck in the Document’s content attribute.

If no YAML Front Matter is provided, Jekyll will not generate the file in your collection.

<!-- vertical-slide -->

### Step 3

Optionally, by setting the output key to true in your collection metadata in your _config.yml:

```yaml
collections:
  slides:
    output: true
```

Jekyll will produce a file for each document in the collection.
For example, if you have

```sh
_slides/jekyll/intro_to_jekyll.md
```

it will be rendered using Liquid and the Markdown converter of your choice and written out to 

```sh
_site/slides/jekyll/intro_to_jekyll.html
 ```

<!-- next-slide -->