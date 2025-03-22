---
title: Why Astro
slug: why-i-like-astro
publishDate: 8 Dec 2023
description: I really like developing projects using Astro, here's why
---

I've had the good luck to be able to work on a couple of [Astro](https://astro.build/) projects professionally in the last few months, and have since decided to build out this little blog in Astro.  I thought I'd take a quick moment to explain why Astro appeals to me.

I've been able to work on a pretty wide variety of projects as a developer in the past few years - but all of those projects fall into one of two categories - static sites or SPAs.  Some of the static sites of worked on would have benefitted from some light interactivity and conversely some of the SPAs have contained a page or two which really could have been static and require no Javascript at all.

I think of Astro as a framework which bridges this gap between static sites and web apps.  

Astro gives developers the ability to ship no javascript by default - everything compiles down to just HTML and CSS - but also to easily opt-in to shipping just the javascript you need to provide the desired interactivity.

I appreciate that Astro's default is to ship no JS, which feels like the _right thing_ to do.  [I like shipping static sites](/blog/static-sites-101/) so that users can use the site even without JS enabled, and almost always this results in a more lightweight and performant site.  But sometimes you just want that bit of interactivity to elevate certain areas, or to allow for some additional functionality.

With Astro, you can ship anything across the spectrum interactivity:

- Static Sites (no client Javascript)
- Partial Hydration (some client Javascript interactivity)
- SPAs (requires Javascript to view site)
