
### How it works

With **jekyll new** command, Jekyll generates some of files and folders

```sh
~ $ jekyll new mySite
Running bundle install in _mySite/mySite...
  Bundler: Fetching gem metadata from https://rubygems.org/...........
  Bundler: Fetching version metadata from https://rubygems.org/..
  Bundler: Fetching dependency metadata from https://rubygems.org/.
  Bundler: Resolving dependencies...
  Bundler: Using public_suffix 2.0.5
  Bundler: Using colorator 1.1.0
  [...]
  Bundler: Using jekyll-watch 1.5.0
  Bundler: Using jekyll 3.4.0
  Bundler: Installing jekyll-feed 0.9.1
  Bundler: Using minima 2.1.0
  Bundler: Bundle complete! 4 Gemfile dependencies, 21 gems now installed.
  Bundler: Use `bundle show [gemname]` to see where a bundled gem is installed.
New jekyll site installed in _mySite/mySite.
```

<!-- vertical-slide -->

Running **jekyll build** command, it will search the ```_config.yml``` file..

```sh
~/mySite $ jekyll build
Configuration file: ~/mySite/_config.yml
            Source: ~/mySite/
       Destination: ~/mySite/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 1.284 seconds.
 Auto-regeneration: disabled. Use --watch to enable.

```

It will take all file in the ```Source``` folder

**process** them if they need it

And **transferr** them to the ```Destination``` folder

**All** files but ones starting with ```_``` character, that will be used for special purpose

<!-- vertical-slide -->

### Wich file it will process and wich only transferred?

Jekyll will process all files with a **YAML Front Matter**

```yaml
---
layout: post
title: Hello
---

<p>Hello!!</p>
```

make them available in memory and make them usable by the **Liquid templating engine** and **Jekyll tags**.

{% raw %}
```liquid
</html>
      <h1>{{ page.title }}</h1>
      <div class="wrapper">
            {{ content }}
      </div>
</html>
```
{% endraw %}

All the other ones, will be only copied

<!-- vertical-slide -->

If you want the regeneration to happen every time a file is changed, just use **jekyll build --watch**:

```sh
~/mySite $ jekyll build --watch.
```

Or to preview the site with the built-in development server use **jekyll serve**:

```sh
~/mySite $ jekyll serve 
```

And browse to [http://localhost:4000](http://localhost:4000)

<!-- next-slide -->