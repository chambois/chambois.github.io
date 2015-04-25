---
layout: post
title:  "Front-end fun times"
date:   2014-12-03 15:06:00
categories: 
---

Beautiful software often is the product of a symphony of reusable cohesive
components. There's one notorious area of a website where typically that sadly 
falls a long way behind in this respect. We can't really blame the team, the
tooling and best practises around this area has been a little slow in catching
up, along with it's difficulty to test and dreaded 'house-of-cards' danger it's
commonly the bane of some developers existence. If you haven't guessed it yet,
were talking about CSS.

![family guy css]({{ site.url }}/assets/css-family-guy.gif)

The tw.com codebase suffers from this 'house-of-cards' symptom. We use
[SASS](http://sass-lang.com/) and our `screen.scss` was our dumping ground for
our styles that we didn't know what to do with. At just over 1500 lines with a
mixture of global styles, we dare not touch it for fear of messing up a style
anywhere on the site. So how could we come to stop adding to this ever-growing
beast? Surely there must be a better way?

![our screen.scss]({{ site.url }}/assets/css-screen.png)

We started introducing the [BEM](https://bem.info/method/) (Block, Element,
Modifier) naming convention. It was a good step, helping by giving us
name-spacing to which we could now refactor with greater peace of mind. Yet we
were still faced with how to effectively deal with how to eventually make
`screen.scss` redundant. How could we come to write CSS that was refactorable
without crazy amounts of manual regression testing? Was there a way we could
chip away at this problem incrementally?  What about reuse? Was there anyway
to make our CSS more 'plugable'? 

So we have ourselves a style-guide. It a good tool, though initially it felt
more an afterthought in the development process, *'Don't forget to add it to
the style-guide... oh yeah right thanks, almost forgot!'*. What if instead we
started with the style-guide? We could even use it as a design tool, almost
like lego blocks...

After some research we came across the [Atomic
pattern](http://bradfrost.com/blog/post/atomic-web-design/) proposed by [Brad
Frost](http://bradfrost.com). If you haven't checked it out yet, it might
just be the CSS practise you've been needing all this time. Reuse. Self
contained. Plugable. Now we're talking! Who knows, we might even be able to
unit test our atoms, molecules, and organisms...

![css atoms]({{ site.url }}/assets/css-atoms.png)

We now have reusable components, our lego blocks. If we need to create a new
search molecule, it's just a matter of plugging our button atom in alongside
our input text atom and viola! `screen.scss` will eventually become redundant,
at which point we'll pop the champagne, yet we've got a fair road ahead to
bring everything into the Atomic pattern before we can.

The pattern has also simplified our functional testing page models, giving us
the same reuse here for our page selectors and doing away with large page
models that were all doing the same thing but for a different class name here
or a slightly different html structure there.

Looking ahead we're trying to figure out how best to handle javascript related
only to molecules and organisms. Also we're hoping to play with a CSS
regression testing library like
[BackstopJS](https://github.com/garris/backstopjs) to achieve a refactoring comfort
level in CSS the likes we've never seen...

If you're interested you can find our style-guide here
<http://showcase.thoughtworks.com/style-guide>

### References
 - SASS: <http://sass-lang.com>
 - BEM: <http://bem.info/method>
 - Atomic pattern: <http://bradfrost.com/blog/post/atomic-web-design/> 
 - Brad Frost: <http://bradfrost.com> 
