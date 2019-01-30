---
date: "2010-01-14"
title: "The Web Strikes Back: Web Components"
slug: "the-web-strikes-back-web-components"
description: "An opinionated article about WebComponents and related frameworks, my personal history, the future ahead and a bunch of useful info in case you're interted in checking WebComponents out"
image: https://res.cloudinary.com/mhdev/images/f_auto,f_auto,w_900/v1547330779/blog/defaultImages/covers/7/italian-mountains.jpg

tags : [
    "WebComponents",
    "Opinions"
]
categories : [
    "Projects",
]
---

I managed to find a Star Wars related title for my second post, this alone should be enough to keep you reading the whole article 😁.

## TL;DR;
WebComponents are one of the few technologies that I love and I want to see succed and flourish, after losing hope and almost giving up things are looking much better now, the current tooling allows us to use WebComponents from different vendors, and some frameworks out there are making WebComponents creations easy as pie.

## Why? What problem do they solve?

I am not capable to a proper introduction to WebComponents, so I'll focus on why use them and what problem do they solve, which is, if you think about it, the reason why any piece of tech exists, to solve a given problem. 

I worked in small and huge companies and one recurring problem is distributed frontend, if you are working in an application that has multiple components let's for argument sake say Header, MainContent, SecondaryContent and Footer, how do you make independent changes to those components, potentially itearate over different ideas, approaches, versions, run A/B testing without the whole process be a massive pain for everybody and manageable at scale? I can tell you that is one big problem where there is not a solution that fits all the usecases.

There are tons of solutions out there, one of the best solutions I had the pleasure of working with is [Open Components](https://github.com/opencomponents/oc) (please check it out, it's an amazing project and I had the pleasure to meet some of the folks working on it, lovely people!) but event that is not 100% quite there in my opinion, global styling, components communication, code reuse, version management are still a problem (beware: comparing OCs to WebComponents is like comparing apples and oranges as they are just different in concept, mine is just an example).

> Web Components is a suite of different technologies allowing you to create reusable custom elements — with their functionality encapsulated away from the rest of your code — and utilize them in your web apps. -MDN

I'd like to emphasise the `with their functionality encapsulated away from the rest of your code` which is exaclty the best thing about WebComponents, leveraging the ShadowDom everything is encapsluated away, that means componetns can be used in isolation and if you have a decend enough logic that handles what version to load in your page, the side effects are almost 0, last but not least, they are fully leaveraging the platform and act as native components, so there is no overhead logic like most of the mainstream framework have to make it behave the way a developer is expecting, and speaking of mainstream frameworks, they, in the end, render HTML, so why not use HTML directly?

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

Sounds familiar? That's exaclty the description of a WebComponents!

Now you undestarand why I love them so much, unfortunately for several different reasons I wasn't able to convince the business to use Polymer, so I kept working with it in my own spare time, I built a bunch of components, applications and because of Polymer's love for PWA, I got into love PWAs and Service Workers as well (this part however deserves it own post/series of posts).

Because of my knowledge and experience with Polymer I also landed a new job in Dubai to work on an e-commerce project with a Polymer front end!

It all looks like a fary tale with a happy ending, but we're in the JavaScript world so something bad had to happen at some point.

If you ever had the misfortune of talking with me about frameworks, you know I don't like React, the thruth is, React is incredible, one of the best thing that could happen to the JS world, but it ate the worls away all the tooling started to floating towards it and frameworks who didn't react (see what I did there) fast enough were left behind, and that happened to my beloved Polymer.

> If you've been a JS dev for less than 2/3 years you might never heard of the following bits, if that's the case, first of all you're making me feel old, second, take a minute to appeciate the current JS scene and how much worse was a while ago.

Polymer 1.x and 2.x relied on HTML imports to import different components as dependencies and bower as dependecy manager, React relies on ES6 imports to import different components as dependecies and npm as dependecy manager.

The above is, in my opinion, the focus point on why Polymer failed to become mainstream, Google wanted to push its own standards too hard (HTML imports) and by the time they changed their mind, it was too late, React won the battle and other framework like Vue came about and it was game over for WebComponents at least for me, I moved to Vue for personal projects, and React for work.

## Web Components today

Of course something as good as WebComponents cannot fail because of any given framework is not properly supported, they are after all a [W3C standard](https://www.w3.org/standards/techs/components#w3c_all) all the browsers have full or partial support for [ShadowDom](https://caniuse.com/#search=shadow%20dom) of couse IE and Edge don't support it, but I said browsers, and we all know IE is not one, MDN has an amazing [page](https://developer.mozilla.org/en-US/docs/Web/Web_Components) about web components, there is still the need of some sort of framework to ease some of the pain point and we're well covered:

### Frameworks

In no particular order I'll list here some of the framework I checked out for my blog project(⚠ this is not a comprehensive list at all, only what I personally used):

- **Polymer 3.x** 

    When Polymer 3 got release I was super exited, I was super pumped because they moved to ES6 imports, npm, WebPack as building tool I was ready to fall in love again with Polymer; the only way I can describe my experience is clusterfuck.
    Lack of documentation, half updated components, Polymer's own website not being updated since mid 2017, it was huge mess, my heart broke again and I've moved on

- **[Omi](https://github.com/Tencent/omi)**
    Omi developed by Tencent is quite impressive, it has super nice features like state management built in, it's lightweight, a nice set of developer tools and in active development, one of the downsides is some of the nice feature (like state management) only work if you're on a full on Omi application, it doesn't work with the good ol' `document.createElement`

- **[Stencil](https://github.com/ionic-team/stencil)**
  Stencil developed by the Ionic team is truly awesome, it's a compiler for generating WebComponents that uses all the nice features the modern JS world has to offer: TypeScript, JSX, WebPack integration and more, and the best thing about it is: it has lazy loading built in so you can have a massive library of components but only what's used in the page will be loaded!

### So what do I use then?
The answer is simple, all the above 😁! With a simple PoC I've created, I was able to load different WebComponents from differnt vendors and they are all playing nicely together, when I pushed the limit of my PoC I had Polymer, Stencil and Aframe compoents running in a single page and they were all working properly! At the moment the PoC is on my sandbox repo, I'll polish it up and create its own repo at some point.
As a personal choice for new and bespoke components, I'm using Stencil, having TypeScript support is very nice and I don't have to worry about loading too many components on a given page as it's all sorted for me, but if there is an existing component that I want to use it's a a simple `npm install` away.

### But my chosen framework is {insert here mainstream framework}!

Everybody has a preffered way to do things, framework, tech stack in general, but as you remember from the first section of this post, all the framework, and I repeat *ALL* of them in the end render HTML, this is what the browser undestrands, there is no other way (excluding WebGL) to render something on screen, so WebComponents can be easily integrated with any given framework

## Conclusion

In a world where mostly everything is React and distrubuted front end is a big problem to solve, WebComponents can make the difference, the road to get to the support we have today was not easy but the current scene is truly amazing and I encourage you to give it a try.

Until next time, have a good one.
