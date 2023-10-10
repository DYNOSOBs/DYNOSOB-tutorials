# A speed Introduction to Creating a Website

We will use Jekyll and Github Actions. From:

> Jekyll is a static site generator. It takes text written in your favorite
> markup language and uses layouts to create a static website. You can tweak the
> site’s look and feel, URLs, the data displayed on the page, and more.

### Examples:

- The groups' website: http://web.evolbio.mpg.de/social-behaviour/
- My personal website: https://nikoleta-v3.github.io


### Installation

Details: https://jekyllrb.com/docs/installation/.

### Starting Your Own Website

Let's start by creating a very basic empty website:

```
$ jekyll new myblog
```

Navigate to the blog:

```
$ cd myblog
```

Let's build the site and make it available on a local server:

```
$ bundle exec jekyll serve
```

### Changing Things

- Edit `_config.yml`. Explain things.

- Edit `index.md` explain the small changes will appear immediately. Also explain
what a `layout` is.

- Explain that things should be `markdown` or `html`.

### Deploy the website

- Create a new repository `thnomimarks.github.io`.

- Do `git` things to get the repo updated.

- Edit the config file: 
  - domain: thnomimarks.github.io
  - url: "https://thnomimarks.github.io"
  - Gemfile: comment out: # gem "jekyll", "~> 4.3.2"
  - Gemfile: add line: gem "github-pages", "~> 228", group: :jekyll_plugins

I got all this from: https://docs.github.com/en/pages/quickstart.


### Free Themes

A list of free themes: https://jekyllthemes.io/free.