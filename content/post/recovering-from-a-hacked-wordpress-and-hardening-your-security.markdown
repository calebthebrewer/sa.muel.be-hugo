+++
date = "2015-06-28T12:38:45+02:00"
draft = true
title = "Recovering from a hacked WordPress"
+++

## Introduction

A few weeks ago, I had to [repair a hacked WordPress](/2015/about-that-time-i-dealt-with-a-bunch-of-hackers-on-a-wordpress/) installation.

A lot of the information I needed to successfully clean the WordPress completely of infected files was not centralized in a single guide. So I decided to write one and you are now reading it.

So, your website is hacked, what now? Let's go through the process of making sure that every infection is removed and it never happens again.

In this first part you'll recover from a hack. In a second part you'll learn how to harden the security. I'll publish the second part in a few weeks.

This post is meant to be exhaustive and clear. If you have any suggestions or feel like something is missing or unclear, [*please* let me know](mailto:s@muel.be?subject=Suggestions%20for%20the%20post%20about%20recovering%20from%20a%20Wordpress%20hack).

## Disabling all plugins / going into maintenance mode

The first thing you should do is avoiding further infections. **Disable EVERY plugin**. We'll reactivate them later on.

I'd also put the website in maintenance mode. This requires, ironically, a plugin called [WP Maintenance Mode](https://wordpress.org/plugins/wp-maintenance-mode/). Install it, write a quick message for your visitors and enable it.

## Take a backup

Backup your complete WordPress folder and database. You can download all the files using FTP or SSH and export the database to SQL statements using something like [phpMyAdmin](http://www.phpmyadmin.net/home_page/index.php) or the customer panel of your host (CPanel, DirectAdmin...). Don't store the backup on your webserver as the hackers could also infect this backup.

## Restore the original WordPress files

Download [a fresh copy of the version of WordPress](https://wordpress.org/download/release-archive/) you were using (which should always be the latest one). Unpack it and replace the directories *wp-admin* and *wp-includes* completely with the copy you just downloaded. Do the same with every file in the root folder and remove every file in your root that is not in the downloaded copy except for *wp-config.php*. The **only folder left untouched should be _wp-content_**. WordPress also doesn't include the *wp-config.php* file so that should also be preserved (we'll inspect this file later on in this guide).

## Clearing the cache

Delete the folders *wp-content/cache* and *wp-content/plugins/widgets*. They will be automatically recreated.

## Upgrade to the latest version

If you're not on the latest version of WordPress, then update ASAP. I'd recommend using [these extended instructions](https://codex.wordpress.org/Upgrading_WordPress_-_Extended_Instructions) instead of the built-in updater, but the built-in updater should be fine for most infected websites.

**Upgrade all your themes and plugins** while you're at it.

## Restore the original themes and plugins

In this step we're going to restore the original theme and plugin files like we did a with the original WordPress files. Download the [themes](https://wordpress.org/themes/) and [plugins](https://wordpress.org/plugins/) from wordpress.org or from the website of the publisher of the plugin or theme (for premium/payed versions). All you need to do is unpack the files into their respective directories in *wp-content/themes* and *wp-content/plugins*. Make sure there are no other files than the ones you just replaced in both of these folders.

NB: some plugins (e.g. plugins containing [dropins](http://wpengineer.com/2500/wordpress-dropins/)) like [WP Super Cache](https://wordpress.org/plugins/wp-super-cache/) also put PHP files in your *wp-content* directory.

## Search and delete infections in your files

The only infected files left could be stored in the subfolders of *wp-content* that we haven't looked into yet.

### languages

If your WordPress is in English, you can safely delete the contents of the *languages* folder, otherwise you should download the translation in your language and put in the *wp-content/languages* while deleting everything else in it.

### upgrade

The folder *upgrade* in *wp-content* is used by WordPress' built-in updater and should always be empty except for when you're updating of course.

### uploads and other folders

Next up: search every other folder in *wp-content* for PHP and server configuration files and delete files if you think they shouldn't be there. I suggest doing a case insensitive search for _*.php_ and _.htaccess_ and carefully inspecting the results.

	find /path/to/wordpress/wp-content/uploads/ -iname "*.php" -or -iname ".htaccess"
	
You probably shouldn't have any PHP or .htaccess files in *wp-content/uploads/someyear/*.

Finally search all the remaing files for typical code injections. PHP injections usually contain the functions *eval* and *base64_decode*.

	egrep 'eval(|decode(' -r -H /path/to/wordpress/wp-content/

## Search and delete infections in your database

## Using *Exploit Scanner* and *Sucuri Security* to detect further infections

## Restoring your website

## Sources