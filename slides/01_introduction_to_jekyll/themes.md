
### Themes

Jekyll has an extensive theme system that allow to customize your site’s presentation.

They set default **layouts**, **includes**, and **stylesheets**, in a way that can be **overridden** by your site’s content.

There are two way of using a Jekyll theme:

1. copying the theme files in our project direcory

2. install a theme as a ruby gem

<!-- vertical-slide -->

### Installing a theme

To install a theme

* add the theme to your site’s Gemfile:
```sh
 gem 'my-awesome-jekyll-theme'
```
* Save the changes to your Gemfile
* Install to install the theme
* Finally, activate the theme by adding the following to your site’s \_config.yml:

```yaml
 theme: my-awesome-jekyll-theme
```

<!-- vertical-slide -->

### Overriding theme defaults

As said, you can override theme default: you only need to creating your own files with the same name in theme.

As example, if your selected a theme with a **page layout**, simple create a **page layout** file in the **\_layouts** folder (e.g. \_layouts/page.html).

Jekyll will look first to your site’s content, before looking to the theme’s defaults

<!-- next-slide -->