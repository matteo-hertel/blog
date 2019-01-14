---
date: "2010-01-14"
description: "The Web Strikes Back"
title: "The Web Strikes Back"
---

I managed to find a Star Wars related title for my second post, this alone should be enough to keep you reading the whole article 😁.

## TL;DR;
WebComponents are one of the few technologies that I love and I want to see succed and flourish, after losing hope and almost giving up on WebCoponents things are looking much better now.

## Intro


## History
⚠️  Boring stuff ahead about my experience and past mistakes

Since the annoucement of [Polymer](https://www.polymer-project.org) WebComponents have been one of my favourite pieced of tech out there, I remember watching a demo video and being blown away by one simple fact, you could do something like

```js
//note: Polymer was released in 2014 where const wasn't  a thing.
var component = document.createElement('custom-element');
document.body.appendChild(component);
```

and by some sort of magic a piece of functionnality with custom logic, styling and whatnot was there on my screen.

That was seriously mind blowing, in particular because at work, where everything was powered by jQuery and a PHP backend, I was trying to write isolated "components" to integrate with a custom build CMS (yeah, super fun) and I ended up writing a my own WebComponents without realising it.

Based on a library that I wrote called [MH_Widget](https://github.com/matteo-hertel/MH_Widget) that was replacing custom markup with valid HTML ([here's](https://github.com/matteo-hertel/MH_Widget/blob/master/Example/index.php#L59) an example, please excuse my PHP) I basically had a static WebComponents implementation done, the only thing needed was hook it up with with JS to make it fit my needs:

- I wanted to be able to have as many instances of a component in any page as I wanted.
- Each component should be isolated and not affecting the outside world.
- Each component should have it's own independent styling.
- Each component should work in isolation.
- The whole thing should be as fast as possible with as little overhead as possible.

Sounds familiar? That's exaclty the description of what WebComponents are doing!

Now you undestarand why I love them so much, unfortunately for several different reasons I wasn't able to convince the business to use Polymer, so I kept working with it in my own spare time 

## Conclusion

Until next time, like subscribe and click on the bell icon to receive notifications.
