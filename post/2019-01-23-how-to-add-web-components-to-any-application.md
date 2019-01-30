---
date: "2010-01-20"
title: "How to add Web Components to any application"
slug: "how-to-add-web-components-to-any-application"
description: "After spending a bit of time having the very basics of the blog done, I've not published it and planning for the future"
image: https://res.cloudinary.com/mhdev/image/upload/f_auto,f_auto,w_900/v1548285001/blog/posts/how-to-add-web-components-to-any-application.jpg 
tags : [
"WebComponents",
"Webpack"
]
categories : [
    "Tutorial",
]
---
## TL;DR; 
As promised in my [last post]({{< ref "/post/2019-01-20-the-return-of-the-blog.md " >}}) this will be the fist of a series of posts that will cover the technical implementations on how this blog was built and how it works, today on the menu we have Web Components: the original Poc(Proof of Concept) to integrate them with a static site generator and how to add them in every project

## Why whould I add Web Components to an existing project?
I've already covered in a previuos [post]({{< ref "/post/2019-01-20-the-return-of-the-blog.md " >}}) benefits and tradeoff of Web Components, but I can expand a bit more on the integration wiht other projects.

Sometimes you just want things to work right out of the box, npm install something cool you see on github and boom it renders on your page, these days frameworks like Vue or React are making this very easy, except they are not, there is alway sometihing that you have to configure, props to pass, components to wrap, webpack moaning about something. Web Componets are not a silver bullet that takes all this pain away but they have one major advantage, because of the Shadow Dom they are self contained *by default* no matters what's arund them, and this in one major adavantage over all the super cool frameworks out there, if it looks a certain way in a screenshot on a Readme somewhere 99.9% it'll look like that in your project, with one _BIG_ exception, if you are overriding some of the css variables in the `:root` selector they might pick those variables out.

The big exception above is also one of the main strenghts Web Compents have, self contained but at the same time extnsible at will, give it a try, if you are reading this post, at some point a while scolling down you'll see a floating header on the top of the page, with a progressbar indicating how much content is left, if you're from a desktop browser, when opening the console and in the inspector you select the `html` element, you'll see something like

```css
:root {
    --progress-color: #3eb0ef;
}
```
go ahead and change the colour to something else, like `palegreen`
```css
:root {
    --progress-color: palegreen;
}
```

you'll see the progressbar immediately change colour to palegreen.

## Proof Of Concept

two stages: 

Standalone

Webpack

Pushing the limits - Aframe


## Integration with an existing project

## Conclusion


