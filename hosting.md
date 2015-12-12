---
layout: page
title: "Hosting"
description: "Hosting your personal blog? Github and Jekyll are your friends. Read this little how-to.."
keywords: "hosting, github, blog, howto, how-to, personal, jekyll, ruby"
permalink: /hosting/
slug: "hosting"
---

Hosting your personal blog? Github and Jekyll are your friends!

![OctoJekyll](http://jekyllrb.com/img/octojekyll.png "Github + Jekyll")

All you need is ruby and gem:
{% highlight bash %}
[root@freddy ~]# dnf install ruby git
...
{% endhighlight %}
Yes dnf, yes I'm using Fedora, did you forget I'm a Red Hatter? :p

Now you have to make your choice: 

1. Use the default jekyll theme
	* In this case you should pay attention if your plan is to use Github for hosting your website
2. Use a custom theme
	* For that take a look @ [http://jekyllthemes.org](http://jekyllthemes.org)

Ok let's start with option one, in that case you have to run:
All you need is ruby and gem:
{% highlight bash %}
[root@freddy ~]# gem install jekyll
...
{% endhighlight %}
This will install you the latest Jekyll version (we're on version 3 at moment I'm writing), instead if you want to publish you website on Github you've to stuck on version 2.5.3:
{% highlight bash %}
[root@freddy ~]# gem install jekyll -v 2.5.3
...
{% endhighlight %}
After that let's create a new website and start builtin server for previewing it!
{% highlight bash %}
[root@freddy ~]# jekyll new my-awesome-site
...
[root@freddy ~]# cd my-awesome-site && jekyll serve
...
{% endhighlight %}

Ok let's move to an important step, did you have some other blog you wish to migrate on this beautiful blog platform?

If this is the case, just follow all the steps reported @ [http://import.jekyllrb.com/docs/home](http://import.jekyllrb.com/docs/home) 

You'll find many plugins, one for every blog platform, that will let you import you old posts.

{% highlight bash %}
[alex@freddy my-awesome-site]$ ll
total 36
-rw-r--r--. 1 alex alex  470 Dec 12 09:51 about.md
-rw-r--r--. 1 alex alex  557 Dec 12 09:51 _config.yml
drwxrwxr-x. 2 alex alex 4096 Dec 12 09:51 css
-rw-r--r--. 1 alex alex 1291 Dec 12 09:51 feed.xml
drwxrwxr-x. 2 alex alex 4096 Dec 12 09:51 _includes
-rw-r--r--. 1 alex alex  506 Dec 12 09:51 index.html
drwxrwxr-x. 2 alex alex 4096 Dec 12 09:51 _layouts
drwxrwxr-x. 2 alex alex 4096 Dec 12 09:51 _posts
drwxrwxr-x. 2 alex alex 4096 Dec 12 09:51 _sass
{% endhighlight %}
And you'll find some example post (or your imported old posts) into *_posts* directory:
{% highlight bash %}
[alex@freddy my-awesome-site]$ ll _posts
total 4
-rw-rw-r--. 1 alex alex 1221 Dec 12 09:51 2015-12-12-welcome-to-jekyll.markdown
{% endhighlight %}

Instead if you planned to use a custom theme (Yeah the default one is really basic), all you need to do is: 

* to clone the github repo or extract the archive you downloaded.

* place you previously imported posts under the theme's *_posts* directory 

Finally if there is any Gemfile launch the *bundle install* command on the theme's dir:
{% highlight bash %}
[alex@freddy jekyll-theme]$ bundle install
Using rake 10.4.2
Using addressable 2.3.8
Using blankslate 2.1.2.4
Using chunky_png 1.3.5
Using fast-stemmer 1.0.2
Using classifier-reborn 2.0.4
Using coffee-script-source 1.9.1.1
Using execjs 2.6.0
Using coffee-script 2.4.1
Using colorator 0.1
Using multi_json 1.11.2
Using sass 3.4.19
Using compass-core 1.0.3
Using compass-import-once 1.0.5
Using rb-fsevent 0.9.6
Using ffi 1.9.10
Using rb-inotify 0.9.5
Using compass 1.0.3
Using fastimage 1.7.0
Using hike 1.2.3
Using jekyll-coffeescript 1.0.1
Using jekyll-gist 1.3.5
Using jekyll-paginate 1.1.0
Using jekyll-sass-converter 1.3.0
Using listen 3.0.4
Using jekyll-watch 1.3.0
Using kramdown 1.9.0
Using liquid 2.6.3
Using mercenary 0.3.5
Using posix-spawn 0.3.11
Using yajl-ruby 1.2.1
Using pygments.rb 0.6.3
Using redcarpet 3.3.3
Using safe_yaml 1.0.4
Using parslet 1.5.0
Using toml 0.1.2
Using jekyll 2.5.3
Using mini_magick 4.3.6
Using rack 1.6.4
Using tilt 1.4.1
Using sprockets 2.12.4
Using sprockets-helpers 1.2.1
Using sprockets-sass 1.3.1
Using jekyll-assets 1.0.0
Using bundler 1.7.8
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
{% endhighlight %}

So you're just one step closer to complete your blog, all you need now is editing *_config.yml* and setup all the necessary for the theme as (hopefully) described by the theme's author.

In my case I chose one from [https://github.com/nandomoreirame](https://github.com/nandomoreirame)

Now you're ready to see your new blog, just exec the *jekyll serve* command:
{% highlight bash %}
[alex@freddy www.alezzandro.com]$ jekyll serve
Configuration file: /home/alex/Documents/www.alezzandro.com/_config.yml
            Source: source
       Destination: _site
      Generating... 
                    done.
 Auto-regeneration: enabled for 'source'
Configuration file: /home/alex/Documents/www.alezzandro.com/_config.yml
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.

{% endhighlight %}

**Please note**: *If you'll experience some issue while running *jekyll serve* command on a custom theme, please ensure you removed any type of *Gemfile* from you directory! :)*

Now feel free to edit or customize the theme while *jekyll serve* is running, it will update the website in realtime showing you the changes after a simple page refresh!

If your website is almost complete all you need to do is to start the Github upload process!


