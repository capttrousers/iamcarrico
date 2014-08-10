---
layout: post
title:  "Jekyll Workflow Part 1: Building a Site"
date:   2014-09-10 12:00:00
categories:
  - jekyll
  - yeoman
---

[Jekyll](http://jekyllrb.com/) has become one of the best static site generators, rising to popularity in no small part because of its use on [GitHub Pages](https://pages.github.com/). It is incredibly simple, and easy to begin making awesome static sites or blogs, with very little effort. This month, I am doing a 4 part series of blog posts on how to create, deploy, and automate a site on Jekyll, all while ensuring it is as performant as possible. These tools are all used on my own site, and several smaller sites that I have worked on, and the code is all available on GitHub.

## Creating a site

First off, make sure that all required dependencies are installed. For the Ruby pieces of Jekyll, only [Bundler](http://bundler.io/) is needed. Everything else will run through [Node.js](http://nodejs.org/download/), and to install the required npm packages:

```bash
$ npm install -g yo bower gulp generator-poole
```

Now that everything is installed, creating a Jekyll site is as easy as using [Mr. Poole, the Jekyll Site Generator](https://github.com/iamcarrico/generator-poole):

```bash
$ yo poole
```

Yeoman will ask you a few questions about your project, and voilà, a fully-featured Jekyll site will be born. Just for you.

## But it is ugly!

Well, yes. But the markup is pretty. And that is what really matters, isn't it?

More importantly, all CSS and styling have been torn away so that you have full control of your Jekyll site from Day 1. It is built to be ultra-flexible, and simple to generate the perfect looking site. It makes no asumptions on the best way to do that, except giving the developer Sass and some base extensions to start with.

## How do I use it?

Glad you asked, this is where Mr. Poole has worked hard to get the site exactly what it needs. Most of all, it has been finely tuned to make development as easy as possible, while including many best-practices.

### Navigation

Navigation is controlled by the data within ```_data/navigation.yml```. By putting navigation inside a Yaml file, we can add on 'active' and 'active-trail' classes when we are on the active link. A new link can be added easily by adding something like this to the navigation.yml file.

```yaml
- name: Contact
  url: /contact/
```

### Gulp / Browser Sync

The true power of Mr. Poole's power lies within the Gulp scripts that will automate many frontend tasks for you. It will compile your sass, include vendor-prefixes, minify images, run a development server with [BrowserSync](http://www.browsersync.io/) and deploy to [GitHub Pages](https://pages.github.com/).

To compile all of our Sass files using compass, use:

```bash
$ gulp sass
```

To ensure all of our images are optimized:

```bash
$ gulp images
```

To build our Jekyll site, and serve it using BrowserSync. This will watch our files and ensure the proper tasks are run for us on their change. It will also automatically update our site, without the need for a refresh, all through BrowserSync.

```bash
$ gulp server
```

To build our site for production, and save the result in '_site':

```bash
$ gulp build
```

To build the site for production, and deploy that code to our gh-pages branch for us:

```bash
$ gulp deploy
```

### Asset pipeline




## More information

This post is just the first in a four part series on how the generator was built, and the code that runs it. Although all of this power is given for free using [Mr. Poole](https://github.com/iamcarrico/generator-poole)
