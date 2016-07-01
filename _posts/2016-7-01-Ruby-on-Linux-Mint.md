---
layout: post
title: How to Install Ruby and Jekyll on Linux Mint 17.3
---

As I said in my first post, I'm using Jekyll, Git, and Github Pages to build, version control, and host this blog. One workflow you can have is writing your posts locally and pushing them to Github where Github builds the site for you. Another workflow is writing your posts locally, and building and viewing your website locally before pushing to Github. This second workflow allows for things to break without affecting the public website. For instance, I'm thinking of making this blog's style match the style of my [main website](http://pisanifamily.info/will/Index.html), but I'm not super familiar with Jekyll's structure and way of doing things. So if I inadvertently break something, my mistake won't affect you, my readers. I had wanted to use this workflow for a while, but I ran into error trying to install Ruby and the github-pages gem. I've finally figured it out and I'll share my solution here.

My initial error was trying to install the github-pages gem using the Ruby and rubygems version from the Linux Mint repositories. Turns out that Jekyll needed a more recent version of Ruby than the repositories carry. I don't remember how I tried going about installing Ruby and rubygems, but it definitely wasn't the right way. The right way for me was following TechAdmin's [guide](http://tecadmin.net/install-ruby-on-rails-on-ubuntu). I didn't install Rails, though. The only error I ran into was a CA error upon trying to run ```curl -sSL https://get.rvm.io | bash -s stable```. The solution was to create a .curlrc file in ~/ with the following lines:

```
capath=/etc/ssl/certs/
cafile=/etc/ssl/certs/ca-certificates.crt
```
My only deviation from the above linked guide was right after installing RVM (Ruby Version Manager): I sourced a file specified by RVM during installation, not the file in the guide. After installing Ruby 2.2.4, I ran ```gem install github-pages``` as suggested by [Barry Clark](https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/). This will install Jekyll and all dependencies. Once installed, move into the root directory of your Jekyll website and run ```jekyll serve --watch```. Now you can view your website at ```http://0.0.0.0:4000```. Enjoy!
