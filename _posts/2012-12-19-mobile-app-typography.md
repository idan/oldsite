---
layout: post
title: The Sorry State of Native App Typography Licensing
---

Lately, I’ve been doing a lot of app-focused design work. By now, the [benefits of good typography](http://affect.media.mit.edu/pdfs/05.larson-picard.pdf) has practically become a truism, for the web in particular and screen-bound products in general. Coming from the web, I was in for a rude awakening when I first looked into font licensing for native mobile apps.

Licensing typefaces for use in mobile apps is a lot like licensing for the web was a few years ago: nonstandard, confusing, and expensive. __It is inexplicably harder and pricier to license type for native apps than it is for the web.__

There is no material reason why mobile type licensing should be more difficult than webfont licensing. In fact, it has more in common with the older desktop-flavored licensing than the newer webfont licensing. The omission of convenient, reasonably-priced mobile licensing is a surprising fumble by the foundries and their resellers.

## Deja Vu: The Rocky Road to Web Type

The web instigated a cultural and technical shift for the notoriously conservative foundries. Before web type, their business was selling an expensive niche product to expert users in a controlled, inherently limited technical setting—individual computers. Fear of piracy coupled with the inherently readable nature of web assets spooked the foundries at first. They weren’t web people. How would they serve up all of these fonts without giving away the shop and without browser-level protection? How would they handle an ever-changing support matrix of platforms, browsers, and versions? I imagine that the web looked like a giant headache for them at first blush, especially because most of them didn’t have serious in-house web expertise at the time. Remember that these are companies which think and operate more like big-media licensors. Their entire worldview revolves around licensing (and protecting) their valuable content, which is trivially stolen in digital form. Their licensing models bear more similarity to media than to software, rife with restrictions on when, where, and how you are permitted to use their products.

It wasn’t until hosted webfont services like [Typekit](http://typekit.com) came along that foundries were willing to dip their toes in the water. Relieved of the need to prepare, store, serve, and bill for usage of their typefaces on the web, foundries gradually accepted the web as another revenue stream. Most now offer the option to license their webfonts directly in addition to the hosted resellers.

A quick tour of my favorite foundries reveals that while most make webfonts a plain option alongside desktop licenses, almost none even _mention_ the possibility of licensing typefaces for use in apps. Instead, they rely on my implicit understanding that the desktop license of “up to _x_ CPUs” means that a thousand mobile app installs containing their typeface requires a “desktop” license for a thousand CPUs.

## A Tale of Two Markets

Shopping for app-embedding licenses is an experience of oddly contrasting flavor: I simultaneously feel like I’m in the dodgy part of the flea market and the white glove, high-roller section in the back of the casino.

The dodgy part comes from the lack of list prices. Stores which lack pricetags give the seller an opportunity to invent a different price for every customer. I’m not saying that the foundries are engaging in pricing hijinks; that would require effort that I don’t think they care to expend. Still, having to inquire about the price of something that my brain perceives as a commodity is jarring.

At the same time, having to inquire about prices comes wrapped in the enterprisiest luxury language. My needs are lumped in with the _“Need something custom?”_ crowd, but I don’t need something _custom_. I need something _common_, and again the disparity between my expectations and the reality leave me unsettled.

Obviously, expectations are a matter of taste, but I’m not buying avocados in a bazaar, nor am I commissioning a work of art—I’m trying to decide whether to license a typeface for an increasingly common application. I don’t know why foundries aren’t posting explicit prices yet. It might be that they just aren’t seeing that many inquiries yet. I’m loath to speculate which is the cause and which the effect.

## Pricing Disparities

Worse, my experience shopping for these licenses has revealed a very uneven market. Asking around at different foundries has yielded prices like:

* 100€ per cut (one-time)
* 1000€ per cut (one-time)
* 400€ per cut (_per year_!)

I’ve also gotten worse responses: “let us think about that and get back to you,” which indicates that they haven’t yet given the matter any serious thought. All of the above were from name-brand foundries and type designers selling A-grade typefaces. The only conclusion I can draw from the enormous disparities in pricing (and the foundries which haven’t yet come up with something) is that this market is immature. It sucks to be a consumer in volatile markets.

Thus far I’ve only encountered two vendors which treat app developers as a first-class audience today: [Fontspring](http://www.fontspring.com/app-fonts) and [Mobile FontFont](http://mobilefontfonts.com). The selection is comparatively meager, but thankfully, both make a point of how app fonts are all licensable with a one-time fee, which I hope is a harbinger of how the market will behave when the dust settles.

With two concrete vendors that list prices publicly, it’s possible to make some educated guesses about on how the industry will end up pricing _appfonts_, for lack of a better term.

[Mobile FontFonts](http://mobilefontfonts.com) are priced in line with their desktop and webfont families at roughly $50 per cut:

<figure>
<img src="http://f.cl.ly/items/0k3J0y1T1z1e2h0U390J/Screen%20Shot%202012-12-19%20at%203.12.35%20PM.png" alt="Mobile FontFont Pricing Table">
</figure>

On the other hand, [Fontspring’s](http://fontspring.com) market seems to have a default pricing structure which is something else entirely:

<figure>
<img src="http://f.cl.ly/items/3k0o0D0P1c1M3b22343C/Screen%20Shot%202012-12-19%20at%203.52.33%20PM.png" alt="Fontspring Pricing Table">
</figure>

_Holy pricing markup, Batman!_ Desktop and webfont pricing is identical, but appfonts are _ten times_ the price! I have mixed feelings about whether this pricing approach makes sense. It’s unclear to me whether we’re underpaying for web type or we’re being gouged when it comes to appfonts.

On one hand, making quality type is a labor-intensive process. Every font produced is the result of an eternity of work. The higher up the quality scale you go, the more work is invested in polishing up the esoteric bits of the typeface. [Price discrimination](http://en.wikipedia.org/wiki/Price_discrimination#Third_degree_price_discrimination) makes sense here—the audience for this good is diverse in the pricing they will bear. Tying pricing to traffic seems to be a reasonable heuristic for ability to bear costs.

I suspect that the foundries are hearing that developers really care about appfonts being a one-time purchase, and rather than relying on the honor system when it comes to choosing an appropriately-sized pageview license, they are asking customers to pay a fixed rate—sacrificing some of the high-end revenue potential in exchange for a higher fixed price which the low end can still swallow. If we assume that app installs is the equivalent of pageviews, a 10× pricing scheme implies that the foundries assume most customers will have at most 10× installs, or 5,000,000. Here, the subsidizing is reversed: customers with less than five million installs are effectively subsidizing the handful of customers with more.

Unfortunately, this model breaks some of my expectations, specifically the one which expects something with ten times the price to deliver commensurate value. App fonts aren’t materially different than their desktop or web cousins. This pricing dichotomy is the business equivalent of a [code smell](http://en.wikipedia.org/wiki/Code_smell)—an indication that something about the model isn’t fully-baked. 

I hope that the foundries will have a change of heart about variable pricing for appfonts. $200-300 is a prohibitive amount for many developers to spend on an experiment. Personally, I might spring for a particularly tasty face—hey, some people like shoes, others like cars, I have a weakness for nice type—but I’m cognizant of the fact that webfont pricing has anchored customer expectations. Foundries have already made peace with the fact that there’s little way for them to tell if I’m buying the appropriate level of webfont license; I don’t see how app installs are different.

More than that, I’ve found that a modicum of time invested in making something look nice helps developers slog through the implementation obstacles and bring a product to completion. They forge an emotional bond with their embryonic product, helping them through the gestation. Democratizing appfonts could do good for the foundries’ bottom lines while helping more projects survive to see their first users.


## The Bottom Line

If you’re a foundry, what the hell are you waiting for? There’s an unserved market that you could enter right now. If you have Truetype or Truetype-outline OTF versions of your typefaces, you have everything you need to sell to both iOS and Android developers _today_. Pay your lawyers to draft a sensible clause in your “desktop” license for mobile embedding, add pricing line-items to your e-commerce backend, and let us buy your wares without feeling like we stepped into the bazaar or the art gallery.

And if you really care about our business, remember that mobile developers aren’t the same desktop audience you’re used to serving. Design a pricing scheme that makes sense for this audience and you’ll see faster adoption—and a corresponding revenue stream.

_Discuss this post on [Hacker News](http://news.ycombinator.com/item?id=4945043) and [Twitter](http://twitter.com/idangazit)._

_Update: The endearingly plainspoken [Monokrom Type Foundry](https://monokrom.no/) reached out to me [on Twitter](https://twitter.com/monokromfonts/status/281555158767378432) to point out that they have standard app-licensing terms, as well as a refreshing default of one included webfont domain per font purchase. Go check ’em out—their catalog is small but beautiful, and indie foundries like these are well worth supporting._
