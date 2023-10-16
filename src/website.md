# A Speed Introduction to Creating a Website

This is a very quick and simple introduction on creating and 
putting online a personal or any other website. 
We won't delve into the details of making our website
 pretty or content-rich, but we will provide links to 
more information if you are interested in properly setting up a website.

The tools we will use are Jekyll and GitHub Pages.

We will use Jekyll to build the website and GitHub Actions 
to deploy it and put it online.

What is Jekyll? From the official website:

> Jekyll is a static site generator. It takes text written in your favorite markup language and uses layouts to create a static website. You can tweak the site's look and feel, URLs, the data displayed on the page, and more.

What is GitHub Pages?

Here are two examples of websites that use Jekyll:

- The group's website: [http://web.evolbio.mpg.de/social-behaviour/](http://web.evolbio.mpg.de/social-behaviour/)
- My personal website: [https://nikoleta-v3.github.io](https://nikoleta-v3.github.io)

My personal website also uses GitHub Actions. How can we tell? Well, it's right there in the name, but we will get to that.

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