---
title: "Building This Website"
permalink: /art/this-website/
excerpt: "An overview of how this website was built"
header:
    #image: /assets/images/construction.png
    teaser: /assets/images/website/site_tech.png
---

This website is built using the following 3 core components:

1. [Jekyll](https://jekyllrb.com/) - a Ruby-based static site generator

2. [GitHub Pages](https://pages.github.com/) - free site hosted from GitHub

3. [Google Domains](https://domains.google/) - domain name hosting by Google

Rather than re-invent the wheel and describe every step of the website
generation and hosting process, below will be a collection of links to
tutorials that provide the step-by-step instructions anyone can use to
create a static website similar to this one.

**Step 1: Establishing a GitHub Pages site**

GitHub allows each user to create one "user site" and unlimited "repository
sites", see their [documentation](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages) for more information.
So the first thing to do is create a GitHub repository called
`<username>.github.io` which is where your website code will go.

Note, building a website this way means that the [source code](https://en.wikipedia.org/wiki/Source_code) behind your website will be publicly available!
For this reason, no confidential or private information should be added your
source code.
But, this also means the source code for *this website* is [available](https://github.com/elbeejay/elbeejay.github.io)
for you to use as a starting point or for reference when building your own
website. In fact, this idea of building off of and adapting existing code to
fit your own needs is common-practice in the open source world.
This website used the [source code](https://github.com/sestus/mikemylonakis.com)
behind [this other website](https://mikemylonakis.com) as a jumping off point.


**Step 2: Using Jekyll**

There are a set of [instructions](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll)
provided by GitHub which provide details about their support for Jekyll site
integration.
They provide information about how to configure your code repository, how to
enable website hosting, as well as instructions and links for getting
Jekyll setup on your local machine.

Once that is configured, you'll want to actually use Jekyll to define and
populate your website. Jekyll sites come in a variety of different layouts
called "themes". For reference, this website uses the lovely [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme.


**Step 3: Custom Domain Hosting via Google Domains**

If you've hosted your website materials via GitHub Pages using Jekyll, then
you can stop at this point and you should have a website at
`<username>.github.io`. However if you want to host your website at a custom
domain name, such as `jayaramhariharan.com` or `yourname.com`, you need to
purchase the domain name. Google, via Google Domains, is one of many companies
that offer domain registration services.

Once you've purchased a domain name, you simply need to tell GitHub Pages that
you would like to redirect your hosted website to a custom domain name.
Fortunately, GitHub makes this simple and even provides [documentation](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site)
detailing how to do this.

On the other end, you will need to tell Google Domains where the hosted website
material is. The GitHub documentation provides some information on how to do this,
but I also found [this guide](https://dev.to/trentyang/how-to-setup-google-domain-for-github-pages-1p58)
to be very helpful.

That's it! Now you should have a website that can be accessed via the
original GitHub Pages address (e.g. [elbeejay.github.io](https://elbeejay.github.io)
for this website) and/or your custom domain name (e.g. [jayaramhariharan.com](https://jayaramhariharan.com)).
