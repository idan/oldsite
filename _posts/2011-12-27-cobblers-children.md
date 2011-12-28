---
layout: post
title: Cobbler’s Children…
---

…barefoot no longer.

HERRO, internets. In my best [Agent Smith][agentsmith], *we missed you*.

Once upon a time, I had a blog. It was Wordpress; it got hacked. I sulked for a week and left for greener pastures, also known as Twitter. That was sometime in 2007.

The problem is, I really love to write. I have a list of things to write about that has languished in my OmniFocus for the last two years. The lack of a venue for writing has harmed my ability to learn and grow, because understanding of a topic doesn’t truly come until you’ve written about it—and shared that writing with others.

Being the design snob that I am, I couldn’t bring myself to actually use a Tumblr or Posterous, mostly because they were annoying to style and presented barriers to doing some unusual things that I’d like to do. I settled on [Jekyll][jekyll] because it doesn’t get in my way, and it allows me to write in my environment of choice, [iA Writer][iawriter]. Also, I can stick custom markup and stying anywhere I want, even on a per-post basis. Painless [hosting on Github][ghpages] is the cherry on top.

Without further ado, here’s a tour of the thinking, tools, and process that went into building the venue I always wanted for writing. Designers might find it a bit mundane, but I hope it’s an instructive peek into the kinds of considerations that go into the design of a thing.

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

All told, this is a site with a very simple structure, which allowed me to experiment with a few techniques I wouldn’t feel comfortable implementing in something more complex.

With a 20-pixel body size and 140% *leading* (the height of each line relative to the size of the type), we have a baseline grid which is 28 pixels tall. With few exceptions, all type on the page is set to round increments of those 28 pixels, constituting a baseline grid as outlined in Richard Rutter’s now-famous article for 24Ways, *[Compose to a Veritcal Rhythm][verticalrhythm]*. You can <a href=“#” class="togglebaseline">toggle</a> the visibility of the grid on this page to see how it applies. Individual lines of body text occupy one line of the grid, larger headers (together with their  margins) occupy multiple whole lines. Making this technique work for a site with more (and more varied) content is a true headache, but here things are simple enough that I felt comfortable giving it a shot.

Horizontally, I chose to go with the most minimal responsive layout I could. Inspired by [Joni Korpi][jonikorpi]’s lovely site, I settled on a 540-pixel-wide main column which fluidly shrinks down to the mobile minimum of 320. Keeping things proportional, the width of these columns is actually specified in relative units. With a 20-pixel base size for our text, that makes the main column 15-27 ems wide, where one em is equivalent to our 20-pixel base text size.

This also means that the layout you see on a mobile device is essentially the same thing you’ll see on the desktop, but narrower. Newspapers set text in narrow columns with good reason: it aids the reader’s eye in an environment full of distractions and interruptions by reducing location to one dimension. Finding your place in a narrow measure is mostly about remembering how far down the column of text you’ve read. Each line is short enough that finding your place within a line is trivial, and rereading a bit of a line isn’t a steep penalty.


### Relative units: *rems* and *ems*

Another technique I’ve been itching to put into practice is the usage of rems, or *root ems*. Introduced in CSS3, Jonathan Snook [provides a great introduction][rems] to these units. They’re a lovely solution to a common source of headache.

CSS allows you to specify units of two flavors: relative and absolute. Absolute units, like pixels, are what they say on the tin. 20 pixels will always be 20 pixels ([except when they aren’t][ppk-pixels], but that’s out of scope here.)
Relative units like ems and percents are relative to the size of your type. Consider the following CSS:

{% highlight css %}
.foo {
	font-size: 20px;
	width: 10em;
}
{% endhighlight %}

The width of this element will be 10 × 20px, or 200px wide. The following CSS is functionally equivalent:

{% highlight css %}
.foo {
	font-size: 20px;
	width: 1000%;
}
{% endhighlight %}

It’s just harder (for me) to think about it that way. The problem with ems and percentages is that their effects compound:

{% highlight css %}
html { font-size: 20px; }
.outer { font-size: 1.5em; }
.inner { font-size: 2.0em; }
{% endhighlight %}

Type in the innermost div will be 60 pixels tall, not 40: `20px × 1.5 × 2.0`. Simple math, but performing the calculation becomes difficult when your page structure becomes more complex, and doubly so in a modern webapp, where you might be dynamically pulling in reusable chunks of markup in different locations.

The solution is a unit which is relative, but only to the text size specified on the *root* of your document, the `<html>` element. So now:

{% highlight css %}
html { font-size: 20px; }
.outer { font-size: 1.5rem; }
.inner { font-size: 2.0rem; }
{% endhighlight %}

Voilà, no compounding. Outer will have 30px-tall text, and inner will have 40px tall text.

Neat, right? Just remember that [IE<9 doesn’t support this][caniuserems], along with most everything in CSS3.





### But does it work in IE?

Probably not. I haven’t even bothered to check. My highest priority was to write, not to make my site accessible to people using the shittiest browser conceived. I know it’s good form to degrade gracefully, and I’ll get around to fixing things eventually, but my usage of rems as a tool for sizing text means that I’ll have to go back and provide an IE stylesheet in ems, with all the arithmetic that entails. Don’t hold your breath.


<script>

$(function() {
	$(".togglebaseline").click(function() {
			$("html").toggleClass("withbaseline");
			return false;
	});
});

</script>

[agentsmith]: http://youtu.be/glBfBxtJU00?t=40s
[jekyll]: http://github.com/mojombo/jekyll
[iawriter]: http://iawriter.com
[ghpages]: http://pages.github.com
[source]: http://github.com/idangazit.github.com
[readability]: http://readability.com
[serif]: http://en.wikipedia.org/wiki/Serif#Readability_and_legibility
[elena]: http://processtypefoundry.com/fonts/elena/
[100e2r]: http://www.informationarchitects.jp/en/100e2r/
[verticalrhythm]: http://24ways.org/2006/compose-to-a-vertical-rhythm
[jonikorpi]: http://jonikorpi.com
[rems]: http://snook.ca/archives/html_and_css/font-size-with-rem
[ppk-pixels]: http://www.quirksmode.org/blog/archives/2010/04/a_pixel_is_not.html
[caniuserems]: http://caniuse.com/#search=rem