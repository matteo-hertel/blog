---
date: "2010-01-20"
title: "The Return of the Blog"
slug: "the-return-of-the-blog"
description: "After spending a bit of time having the very basics of the blog done, I've not published it and planning for the future"
image: https://res.cloudinary.com/mhdev/image/upload/c_thumb,w_1400,g_face/v1548013171/blog/posts/the-return-of-the-blog.jpg
tags : [
    "Opinions"
]
categories : [
    "Projects",
]
---

## TL;DR;
The first article of the newly published blog, how I got to this point and the plans for the futures

## Published 🎉
The blog is finally plublished at [https://mountaindev.tech](https://mountaindev.tech), the last missing bit was having the CI running.

Now that the blog is published I decommissioned the old blog, old urls and all the services I had running to power the old plaform, including, a production Kubernetes cluster, a sandbox Kubernetes cluster a couple of databases and way too many convoluted DNS records, this is a huge achievement!

## Thech stack

The final tech stack looks like this:

The content source is store [https://github.com/matteo-hertel/blog](https://github.com/matteo-hertel/blog) it holds only the content of the different pages/posts.

The blog itself is a static site generated via [Hugo](https://gohugo.io) with a custom theme called [Slimer](https://github.com/matteo-hertel/slimer) originally a fork of [Ghost's](https://ghost.org/) theme [Casper](https://github.com/TryGhost/Casper) in which I've added:

- Webpack 4.
  - With hot reload between Hugo and the static assets. 
- WebComponents built with [Stencil](https://stenciljs.com/).

The vast majority of the static assets are handled by [Cloudinary](https://cloudinary.com).

The CI is handled by [Travis](https://travis-ci.org/).

The CD is handled by [Netlify](https://www.netlify.com/) the super awesome thing about Netlify is that I it'll deploy a preview to a temp url for each pull request (more on this in a separate post).

The DNS are managed via [Cloudflare](https://dash.cloudflare.com).



## Plans for the future 


## Credits
Cover picture by [Daniel Cheung](https://unsplash.com/photos/cPF2nlWcMY4?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/search/photos/star-wars?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)
