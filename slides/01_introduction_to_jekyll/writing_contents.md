
### Writing contents

One of Jekyll’s best aspects is that you can easly publish and maintain a site or blog simply by managing a folder of text-files on your computer.
<!-- vertical-slide -->

### The Posts Folder

As explained on the directory structure page, the **\_posts** folder is where your blog posts will live

All posts must have YAML Front Matter, and they will be converted from their source format into an HTML page

<!-- vertical-slide -->

### Creating Post Files

To create a new post, all you need to do is create a file in the \_posts directory. 

The file name is important, Jekyll requires the following format:

```sh
YEAR-MONTH-DAY-title.MARKUP
```

For example, the following are examples of valid post filenames:

```sh
2011-12-31-new-years-eve-is-awesome.md
2012-09-12-how-to-write-a-blog.md
```

<!-- vertical-slide -->

### Creating pages

In addition to writing posts,Jekyll cab be used to create static pages, in 2 main ways:

* Placing a named HTML or Markdown files for each page in your site’s root folder.


```sh
├──── index.html
│
├──── about.md
```

* Creating a folder and place an index.html or index.md file in each page folder.

```sh
├──── index.html
│
├──── about/
│ │
│ └── index.md
```

Both methods work fine with the only difference in the resulting URLs.

<!-- next-slide -->