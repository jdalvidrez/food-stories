---
title: Directory
layout: base
date: 2024-10-26
---

# Cards
Even a small website needs a way of organizing content and pages. Xanthan comes with a few ways to do this, and of course more can be added.


## Table of Contents
One familiar approach is to create a table of contents for your site pages, like you'd find in a book. Let's say you have a collection of pages, like student essays for a class project, for which you want to create a table of contents. We can do this automatically, as long as each page has a little metadata at the top of the file in the YML header. It looks like:

```
---
title: My Essay Title
author: Fred Gibbs
summary: This is a short but provocative summary of my essay
---
```

We can use this data to automatically generate links to the essays, like this: 


{% assign pages = site.pages | where_exp: "page", "page.path contains 'essays/'" %}

{% include card-toc.html rows = pages %}



It's not magic! We just need to tell Xanthan to create some links based on the metadata that's found on pages in Xanthan's `essays` folder. We use a little bit of pseudo-code to do this. It looks weird at first, but it makes sense once you get used to the syntax.

- First, we define a variable called `pages` (it could be called anything) that gathers all the metadata  from the files in the essays folder (that's what the page.path contains 'essays/' part does). 
- Then we send that data to our include file (card-toc.html), which has the actual HTML code to generate the cards themselves. 
- You can copy and paste this code on any page where you want to link to other pages. Just change `essays` in the code to the folder where your pages are. 


```
{%raw%}{% assign pages = site.pages | where_exp: "page", "page.path contains 'essays/'" %}

{% include card-toc.html rows = pages %}{%endraw%}
```


---



## Stacked cards
A little fancier than a ToC-style list, we can a generate of a stack of horizontal "cards" in the same way. In terms of gathering data to display, this works exactly like above. But it calls a different include file, which presents a stack of wide and short cards in a vertical display. 

```
{%raw%}{% assign essays = site.pages | where_exp: "page", "page.path contains 'essays/'" %}

{% include card-stack.html cards = essays %}{%endraw%}
```

{% assign essays = site.pages | where_exp: "page", "page.path contains 'essays/'" %}
{% include card-stack.html cards = essays %}


### Optional Tags
You can group and label similar content with tags in page metadata. Let's say you have a set of podcasts from a personal podcast or class project. To keep things organized, I put them in a `podcasts` folder. 

```
---
title: Pocast Episode #1
author: Fred Gibbs
summary: This is a short but provocative summary of my podcast episode
tags:
  - history
  - digital humanities
  - awesome
---
```

{% assign podcasts = site.pages | where_exp: "page", "page.path contains 'podcasts/'" %}
{% include card-stack.html cards = podcasts %}



---

## Grid cards
You can see more cards at a glance if you use a grid layout with slightly smaller cards.

```
{%raw%}{% assign essays = site.pages | where_exp: "page", "page.path contains 'essays/'" %}

{% include card-grid.html cards = essays %}{%endraw%}
```

{% assign essays = site.pages | where_exp: "page", "page.path contains 'essays/'" %}
{% include card-grid.html cards = essays %}

---

## Left Navbar
Another way of getting to pages on your site can be through a nav bar that always stays on the left side of the page. Check out the [left navbar demo page](left-nav-demo).

