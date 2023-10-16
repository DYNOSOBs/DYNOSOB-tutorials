# A Speed Introduction to Creating a Website

This is a very quick and simple introduction on creating and putting online a
personal or any other website. We won't delve into the details of making our
website pretty or content-rich, but we will provide links to more information if
you are interested in properly setting up a website.

The tools we will use are Jekyll and GitHub Pages. We will use Jekyll to build
the website and GitHub Actions to deploy it and put it online.

What is Jekyll? From the [official website](https://jekyllrb.com):

> Jekyll is a static site generator. It takes text written in your favorite
> markup language and uses layouts to create a static website. You can tweak the
> site's look and feel, URLs, the data displayed on the page, and more.

What is [GitHub Pages](https://pages.github.com)?

> GitHub Pages is a static site hosting service that takes HTML, CSS, and
> JavaScript files straight from a repository on GitHub, optionally runs the
> files through a build process, and publishes a website.

Here are two examples of websites that use Jekyll:

- The group's website:
  [http://web.evolbio.mpg.de/social-behaviour/](http://web.evolbio.mpg.de/social-behaviour/)
- My personal website:
  [https://nikoleta-v3.github.io](https://nikoleta-v3.github.io)

My personal website also uses GitHub Pages. How can we tell? Well, it's right
there in the name, but we will get to that.

### Installation

Before you can start building your website, you will need to install a few
things. The dependencies, or the items you need to install for Jekyll, are
outlined on Jekyll's website: https://jekyllrb.com/docs/installation/.

To use GitHub Pages, you will need to create a [GitHub
account](https://github.com). Please note that we will build and deploy our
website for free! You do not need to have a paid account with GitHub to use
GitHub Pages.

For this tutorial, you will have to run commands in the terminal (Mac OS/Linux).
If you are on a Windows machine, you can try downloading [Git
Bash](https://gitforwindows.org). In this tutorial, you
will know that you need to run a command in the terminal because the command
will start with the symbol `$`.

We will also need to [install git](https://git-scm.com/downloads), which is a
version control tool. It allows us to communicate with GitHub, upload (push)
changes, or download (pull) things.

You will need an editor of your choice. I use
[VSCode](https://code.visualstudio.com) (not a paid promotion).

So, here's a checklist of what you need:

- [] Follow the installation steps outlined on the Jekyll website.
- [] Create a GitHub account.
- [] Use the terminal or Git Bash.
- [] Install git.
- [] Have an editor of your choice.

Feel free to reach out if you encounter any installation issues.

### Starting Your Own Website

Let's start by creating a very basic empty website! In your terminal
navigate to where you want the folder of your website. For example
I am going to create the folder in my Desktop.

```
$ pwd

$ cd Desktop/
```

`pwd` is a simple command to know my location. The output is different for
everyone. Here we will run the first jekyll command:

```
$ jekyll new myblog
```

This creates a folder in your computer called `myblog`. You don't believe me?
Type `ls` which lists all items in your current location.

```
$ ls
```

Navigate to the folder.

```
$ cd myblog
```

Let's build the site and make it available on a local server:

```
$ bundle exec jekyll serve
```

This will return a bit of a text but the end includes. Open this url
in your web browser. Here is an example of how the website looks in my safari
broswer.

### Changing the website

Let's apply some minor changes. For example you want to change the
homepage. To do this you need to edit the `index.md` file. Add the folowing
line and refresh the website.

- explain what a `layout` is.

There is another page in the website called about. If we wanted changes
to this we need to edit.

These are low level changes so they appear once you refresh, however,
there are other changes for which you have to rebuild before they appear.
For example all the meta information 

- Edit `_config.yml`. Explain things.

### Deploy the website

Now let's assume we are ready for deployment (we really are not)! 

- Create a new repository `thnomimarks.github.io`.

- Do `git` things to get the repo updated.

- Edit the config file: 
  - domain: thnomimarks.github.io
  - url: "https://thnomimarks.github.io"
  - Gemfile: comment out: # gem "jekyll", "~> 4.3.2"
  - Gemfile: add line: gem "github-pages", "~> 228", group: :jekyll_plugins

I got all this from: https://docs.github.com/en/pages/quickstart.

### Going Forward

This is a very simple and minimalistc guide about createing a website just
to get you familiar and started. You could further develop your our website
refreacling your own style! You want to do this that's awesome and Jekyll
has a lot of guides on this: .

However, sometimes creating your own theme can be hard. Jekyll has a fantastic
comminuty and a lot of people have made their themes availabe online fo free.
You can check this website for free themes or even paid:
https://jekyllthemes.io/free.

Each style has it's on GitHub page and there they explain how to use the theme,
make changes that reflect you and sometimes even how to deploy the website!
I hope you enjoy going down the rabbit whole. In my experience things can take some time and it can become furstraing, however, you gain a lot from setting
up your own website! Like knowlegde in html and if you were to follow
this guie with git.

This is just one way and not the best way!.