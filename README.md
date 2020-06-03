# Alteridem.net

## Theme

The theme was created from the default Jekyll Minima theme.

### Layouts

Refers to files within the `_layouts` directory, that define the markup for your theme.

  - `default.html` &mdash; The base layout that lays the foundation for subsequent layouts. The derived layouts inject their contents into this file at the line that says ` {{ content }} ` and are linked to this file via [FrontMatter](https://jekyllrb.com/docs/frontmatter/) declaration `layout: default`.
  - `home.html` &mdash; The layout for your landing-page / home-page / index-page. [[More Info.](#home-layout)]
  - `page.html` &mdash; The layout for your documents that contain FrontMatter, but are not posts.
  - `post.html` &mdash; The layout for your posts.

### Includes

Refers to snippets of code within the `_includes` directory that can be inserted in multiple layouts (and another include-file as well) within the same theme-gem.

  - `disqus_comments.html` &mdash; Code to markup disqus comment box.
  - `footer.html` &mdash; Defines the site's footer section.
  - `google-analytics.html` &mdash; Inserts Google Analytics module (active only in production environment).
  - `head.html` &mdash; Code-block that defines the `<head></head>` in *default* layout.
  - `header.html` &mdash; Defines the site's main header section. By default, pages with a defined `title` attribute will have links displayed here.

### Sass

Refers to `.scss` files within the `_sass` directory that define the theme's styles.

  - `alteridem.scss` &mdash; The core file imported by preprocessed `main.scss`, it defines the variable defaults for the theme and also further imports sass partials to supplement itself.
  - `alteridem/_base.scss` &mdash; Resets and defines base styles for various HTML elements.
  - `alteridem/_layout.scss` &mdash; Defines the visual style for various layouts.
  - `alteridem/_syntax-highlighting.scss` &mdash; Defines the styles for syntax-highlighting.

### Assets

Refers to various asset files within the `assets` directory.
Contains the `main.scss` that imports sass files from within the `_sass` directory. This `main.scss` is what gets processed into the theme's main stylesheet `main.css` called by `_layouts/default.html` via `_includes/head.html`.

This directory can include sub-directories to manage assets of similar type, and will be copied over as is, to the final transformed site directory.

### Plugins

- [`jekyll-seo-tag`](https://github.com/jekyll/jekyll-seo-tag) plugin ensures your website gets the most useful meta tags. See [usage](https://github.com/jekyll/jekyll-seo-tag#usage) to know how to set it up.

## Usage

### Home Layout

`home.html` is a flexible HTML layout for the site's landing-page / home-page / index-page. <br/>

#### Main Heading and Content-injection

The *home* layout will inject all content from your `index.md` / `index.html` **before** the **`Posts`** heading. This will allow you to include non-posts related content to be published on the landing page under a dedicated heading. *We recommended that you title this section with a Heading2 (`##`)*.

Usually the `site.title` itself would suffice as the implicit 'main-title' for a landing-page. But, if your landing-page would like a heading to be explicitly displayed, then simply define a `title` variable in the document's front matter and it will be rendered with an `<h1>` tag.

#### Post Listing

It will be automatically included only when your site contains one or more valid posts or drafts (if the site is configured to `show_drafts`).

The title for this section is `Posts` by default and rendered with an `<h2>` tag. You can customize this heading by defining a `list_title` variable in the document's front matter.

--

### Customize navigation links

This allows you to set which pages you want to appear in the navigation area and configure order of the links.

For instance, to only link to the `about` and the `portfolio` page, add the following to you `_config.yml`:

```yaml
header_pages:
  - about.md
  - portfolio.md
```

--

### Change default date format

You can change the default date format by specifying `site.date_format`
in `_config.yml`.

```
# refer to http://shopify.github.io/liquid/filters/date/ if you want to customize this
date_format: "%b %-d, %Y"
```

--

### Enabling comments (via Disqus)

Optionally, if you have a Disqus account, you can tell Jekyll to use it to show a comments section below each post.

To enable it, add the following lines to your Jekyll site:

```yaml
  disqus:
    shortname: my_disqus_shortname
```

You can find out more about Disqus' shortnames [here](https://help.disqus.com/customer/portal/articles/466208).

Comments are enabled by default and will only appear in production, i.e., `JEKYLL_ENV=production`

If you don't want to display comments for a particular post you can disable them by adding `comments: false` to that post's YAML Front Matter.

--

### Social networks

You can add links to the accounts you have on other sites, with respective icon, by adding one or more of the following options in your config:

```yaml
twitter_username: jekyllrb
github_username:  jekyll
dribbble_username: jekyll
facebook_username: jekyll
flickr_username: jekyll
instagram_username: jekyll
linkedin_username: jekyll
pinterest_username: jekyll
youtube_username: jekyll
googleplus_username: +jekyll
rss: rss

mastodon:
 - username: jekyll
   instance: example.com
 - username: jekyll2
   instance: example.com
```

--

### Enabling Google Analytics

To enable Google Analytics, add the following lines to your Jekyll site:

```yaml
  google_analytics: UA-NNNNNNNN-N
```

Google Analytics will only appear in production, i.e., `JEKYLL_ENV=production`

--

### Enabling Excerpts on the Home Page

To display post-excerpts on the Home Page, simply add the following to your `_config.yml`:

```yaml
show_excerpts: true
```
