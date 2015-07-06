+++
date = "2015-07-28T16:03:24+02:00"
draft = true
title = "An introduction to hugo, a static site generator"

+++

## A good blogging platform

What makes a good blogging platform? Well, that depends on the blogger. Programmers would need different features than make-up bloggers. As a programmer I need to be able to easily integrate pieces of code with syntax highlighting in my posts and I'd prefer writing them in my favourite text/code editor instead of a WYSIWYG editor.

## Jekyll

A static site generator like [Jekyll](http://jekyllrb.com) fulfills all my needs as a programmer/blogger:

* posts are written in [Markdown](http://daringfireball.net/projects/markdown/), Textile, HTML...
* you don't need to setup a database and any simple web server will do the job
* once setup, you don't need to think about updates etc.
* extremely developer friendly (e.g. publish a post using the command line) and open source
* works great with source code control

However, after a while, you start to notice the little things that make Jekyll a lot less simple than it looks like.

* it's written in Ruby and some of its dependencies aren't (bug free) available on ~~all platforms~~ Windows
* setting it up can be quite bothersome, again, especially on Windows

## Hugo

A few other static site generators [have sprung up](https://www.staticgen.com) since Jekyll's success.

The one that caught my attention was [hugo](http://gohugo.io). It has all the goodness from Jekyll, but it's way easier to setup. Hugo itself is written in [Go](http://golang.org), but they build [executable binaries](https://github.com/spf13/hugo/releases) for a lot of platforms. So you don't need to install anything else. Even compiling it yourself isn't that hard.

The process of creating a new website is very similar to Jekyll. The `hugo` command literally explains itself (`hugo help`) and the [documentation](http://gohugo.io/overview/introduction/) on its website should suffice for most users.

I've succesfully migrated my [Jekyll blog](https://github.com/SamuelDebruyn/samueldebruyn.github.io/tree/5f5719a9d4519f8fbd4cdfffa2a10b3f066401ef) to [hugo](https://github.com/SamuelDebruyn/sa.muel.be-hugo) and haven't regretted it ever since.