---
layout: post
title: Cobbler’s Children
---

HERRO, internets. We missed you.

Once upon a time, I had a blog. It was Wordpress; it got hacked. I sulked for a week and left for greener pastures, also known as Twitter.

The problem is, I really love to write. I have a list of things to write about that has languished in my OmniFocus for the last two years. The lack of a venue for writing has harmed my ability to learn and grow, because understanding of a topic doesn’t truly come until you’ve written about it—and shared that writing with others.

Being the design snob that I am, I couldn’t bring myself to actually use a Tumblr or Posterous, mostly because they were annoying to style and presented barriers to doing some unusual things that I’d like to do. I settled on [Jekyll][jekyll] because it doesn’t get in my way, and it allows me to write in my environment of choice, [iA Writer][iawriter]. Also, I can stick custom markup and stying anywhere I want, even on a per-post basis. Painless [hosting on Github][ghpages] is the cherry on top.

Without further ado, here’s a tour of the thinking, tools, and process that went into building the venue I always wanted for writing. Designers might find it a bit mundane, but I hope it’s an instructive peek into the kinds of considerations that go into designing something that is meant to be used.

## A technical tour

The [source] for this blog’s structure is public and MIT licensed. Take a look if that’s your thing.

My design goals were simple. This is a repository for writing, and thus people should have an easy time reading it. Here were the key goals:

* **Minimal**: your attention should be focused on the content, everything else should disappear from view.
* **Legible**: large type, set to maximize ease of reading.
* **“Mobile first”**: The site should be easy to read on an iPhone, and by extension, on the desktop as well—not the other way around.
* **Trendy monochrome monogram**: I has it.

Conveniently, these goals are highly correlated. Designing for one tends to help the others.

### Typography

Long-form writing is like a marathon for readers’ eyes. They’re not sprinting down your hundred words, you want to keep them reading for the long haul. It’s important to make that task as easy as possible.

To that end, you generally [want a serif face][serif] for your body text. For reasons passing understanding, many of the themes on popular sites use a miniscule sans-serif font for their body text (I’m lookin’ at you, Posterous). A rich history of type design for print isn’t anachronistic, it’s informative. Those designers figured out what works for humans reading text. Humans haven’t changed, text hasn’t changed—there’s no reason to throw all that away just because we’ve exchanged ink for pixels.

That rich history tells us that body text should be a serif. Not just any serif, but a text workhorse. There are decorative serifs, and swashy serifs, neither of which you want. This is the quintessential typographical challenge: finding a face that at once has character and warmth without demanding the reader’s attention.

I found that serif in the form of Process Type’s [Elena][elena]. The relatively tall height of the lowercase letterforms (the _x-height_) makes for a better reading experience onscreen, where the density of pixels per inch is low (in the neighborhood of 100) compared to print, where things start at 300 dpi. A taller x-height helps readers distinguish between characters on the resolution-poor screen, and thus improves legibility and lowers cognitive load.

This entire site is set in the versatile Elena, which looks lovely at large (_display_) size and for body copy. 

### 100% E2R

Good typography *begins* with the selection of a typeface suited to the task at hand, but it doesn’t end there. Legibility is achieved through thoughtful use of type.

Oliver Reichenstein authored the seminal [100% Easy-to-Read Standard][100e2r], which ought to be required reading for anybody building things for the web. Seriously, stop reading this and go read that now. It’s a better investment of time.

100E2R touches on all the important points of sound web typography. While it may seem a bit prescriptive, these aren’t new rules—they’re very _old_ rules. Our eyes haven’t gotten any sharper in the half-millenium that humans have been setting type on a page.

The default size of body text here is 20px, or 125%. Different typefaces appear to be larger or smaller at a given point size, and while the venerable Georgia looks large and bright at the standard 16px, Elena felt a little cramped.

Another reason for the larger type size is the proliferation of high-density displays. My 15″ MacBook Pro sports a display with 128 pixels per inch, while my desktop display (a Dell <abbr>WFP2007</abbr>) has the same resolution at a larger size, and correspondingly lower pixel density of 99 <abbr title=“PPI”>PPI</abbr>.

The net effect is that text appears smaller on a high-density display. 20px-tall text on my MacBook appears to be about as large as 16px-tall type on my desktop monitor. It’s likely that my audience owns newer machines with high-density displays. It seems a reasonable tradeoff to make text on “normal” monitors largish to ensure that higher PPI monitors never see text smaller than the optical size of 100% on a normal monitor.

### Structure

Just as economics has *micro-* and *macro-* variants, typography can be approached at different scales. If the qualities of a typeface constitute the micro, then the structure of type on a page is the macro view.

All told, this is a site with a very simple structure, which allowed me to experiment with a few techniques I wouldn't feel comfortable implementing in something more complex.

Taking the size of my body type as the fundamental unit of reference, both the horizontal and vertical stucture of the page are defined in 20-pixel increments. With few exceptions, all type on the page is set to a 20px baseline grid as outlined in Richard Rutter’s now-famous article for 24Ways, *[Compose to a Veritcal Rhythm][verticalrhythm]*. <a href=“#” class=“togglebaseline>Click here</a> to toggle the visibility of the baseline grid.





[jekyll]: http://github.com/mojombo/jekyll
[iawriter]: http://iawriter.com
[ghpages]: http://pages.github.com
[source]: http://github.com/idangazit.github.com
[readability]: http://readability.com
[serif]: http://en.wikipedia.org/wiki/Serif#Readability_and_legibility
[elena]: http://processtypefoundry.com/fonts/elena/
[100e2r]: http://www.informationarchitects.jp/en/100e2r/
[verticalrhythm]: http://24ways.org/2006/compose-to-a-vertical-rhythm