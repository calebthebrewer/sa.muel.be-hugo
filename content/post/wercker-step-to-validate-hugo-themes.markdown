+++
date = "2015-07-13T15:35:28+02:00"
draft = true
title = "Wercker step to validate hugo themes"
+++

So last week, I created [a material design theme](2015/material-lite-theme-for-hugo/) for [hugo](http://gohugo.io), a static site generator which I'm [quite fond of](search/?q=hugo).

As I [discovered Wercker](2015/continuous-integration-with-hugo-and-wercker/), an awesome CI tool, I went looking for a way to validate themes with [Wercker](http://wercker.com).

There wasn't any, so I simply wrote a build step for Wercker. The build step validates a hugo theme using [an example site](https://github.com/spf13/HugoBasicExample). It also checks if you included some files required for a future hugo themes site. 

The code for the build step is available at https://github.com/SamuelDebruyn/wercker-step-hugo-theme-check and an example Wercker configuration is included below.

	box: debian
	build:
	  steps:
	    - samueldebruyn/hugo-theme-check:
	        version: "0.14"
	        theme: material-lite