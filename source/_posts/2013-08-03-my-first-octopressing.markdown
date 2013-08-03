---
layout: post
title: "My First OctoPressing"
date: 2013-08-03 11:33
comments: true
categories: [Code]
---

I have to dedicate my first post to the tool thats making it possible - **Octopress**. When I created my previous blog as a Rails app I decided to combine a mixture of static and dynamic content. The page was a real haml page, allowing me the convenience of simply typing what I was talking about without having to worry about how it would be interpreted.

<!-- more -->

I stored the page title, meta content and a few other details in the database. This information was dynamically inserted into each page through a shared layout. When I first heard of Octopress and the idea of a completely static website I knew I had to give it a try.

I worked on an app previously where the user had a wysiwyg editor to enter posts. Combined with a versioning gem to allow for preview and undo. There was special delimiters for source code, the more flexibility I wanted the more code I had to write.

I knew there must have to be a better way to blog.

It just works
-------------

The documentation is great and everything just works as expected. I am using the latest rvm so I switched to `.ruby-gemset` and `.ruby-version`, I got a warning when changing into the directory.

I deployed to Heroku since its more familiar to me.

SEO
---

I didn't have any content so I might have been jumping the gun a bit but I registered my custom domain with Google Webmaster Tools and Bing. I also didn't want any issues with duplicate content. I think Heroku's default of letting u serve your site off 2 domains is not a good one. Turns out rack-rewrite was what I needed:

``` ruby
use Rack::Rewrite do
  r301 %r{.*}, 'http://blog.brentgreeff.com$&', if: Proc.new {|rack_env|
    rack_env['SERVER_NAME'] != 'blog.brentgreeff.com'
  }
end
```

this didn't work too well when using : rake preview, to view the site locally, so I changed this to :

``` ruby
r301 %r{.*}, 'http://blog.brentgreeff.com$&', if: Proc.new {|rack_env|
  rack_env['SERVER_NAME'] == 'blog-brentgreeff.herokuapp.com'
}
```

I didn't like the blog url structure, so I took some ideas from: [this post]

[this post]: http://www.ewal.net/2012/09/08/octopress-customizations/

