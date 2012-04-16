---
layout: post
title: Image Format Inertia
---

Yesterday, Google’s new-but-not-really [WebP image format](https://developers.google.com/speed/webp/) graced the front page of Hacker News, again. [The comments](http://news.ycombinator.com/item?id=3843839) were a predictable mix of “but that’s already been done in `$FORMAT`!” and “Meh, never going to gain traction.”

So what *would* it take for a new image format to gain traction on the web?

## “Good Enough”

The problem that these novel image formats are trying to solve are the wrong problems, in the sense that fixing these problems won’t be enough of a game-changer for the browser vendors to pay attention. Reducing filesize is no mean technical feat, but getting the holy quartet of browser vendors (Google, Apple, Mozilla, and Microsoft) to take action—preferably the *same* action—requires a lot of oomph. Note that I left Opera out, both because of their negligible market share, and because they would do something awesome without much prodding.

Reducing filesize will forever be an incremental affair as new math is discovered for compressing image data. It’s unlikely that we’ll raise the temperature high enough/fast enough to make the [frog jump out of the boiling water](http://en.wikipedia.org/wiki/Boiling_frog). Right now, the only users in the developed world who are hurt by large file sizes are mobile users, but that’s not the crux of the problem. The fact that we can’t deliver images of appropriate resolution to different devices is.

## Responsive Images

If you’ve been living under a rock for the last couple of years, [Responsive Web Design](http://johnpolacek.github.com/scrolldeck.js/decks/responsive/) is being used on more and more sites to provide a tailored experience for the different devices accessing them. In a nutshell, you build the same website you always did (using properly semantic markup, right?) and *style* it in a fashion that responds to the browser’s size and screen properties. The key here is that your styling (CSS) is properly separate from your content (HTML), allowing you to change everything about your presentation. Type, layout, color—anything you can style with CSS is fair game.

The inconvenient elephant in the room is our trusty `<img>` tag. Images which are *content* and not presentational rightfully belong in your markup, but there’s no way to specify multiple sources for a single `<img>` tag. Because of this, authors are forced to choose between two poor options when crafting a responsive website. You may opt to serve up a full-resolution image, providing a good experience on desktops while levying a hefty download tax on mobile users (who will downscale the image anyways), or you can serve up a smaller image and upscale on larger screens—sacrificing quality.

Naturally, smart people have come up with some [lovely](https://github.com/filamentgroup/Responsive-Images) [hacks](http://www.alistapart.com/articles/responsive-images-how-they-almost-worked-and-what-we-need/) that enable authors to serve up different images to different devices. The W3C has even convened a [Responsive Images Community Group](http://www.w3.org/community/respimg/) to get a standard in place, but like all things W3C, don’t hold your breath.

## And WebP?

There are two ways to solve the responsive image dilemma. HTML or CSS can allow authors to specify multiple sources for the same image, or images can get smarter about providing multiple  quality-versus-size breakpoints, in a manner reminiscent of Ogg Vorbis’ [Bitrate Peeling](http://en.wikipedia.org/wiki/Bitrate_peeling). With this sort of enhanced image format, browsers could stop reading image data from the server whenever they have enough data to show a satisfactory level of detail.

After a brief adolescent period of designing in parallel for mobile devices, we’re emerging into an adulthood where we design for the growing infinty of screen geometries. Responsive images are a critically absent tool in our arsenal. Designing an image format that attacks this problem would have a much greater impact than simply reducing filesize, and with all eyes on mobile, I’d bet that would get the attention of the browser vendors.