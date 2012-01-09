---
layout: post
title: Nonrendering elements in D3.js
---

I just blew 24 hours chasing broken behavior in [D3.js](http://mbostock.github.com/d3/) which could have been prevented if:

* I were a smarter bug-hunter. Or just smarter.
* I dug a little further back into through the commit history to find [this commit](https://github.com/mbostock/d3/commit/11c1e7a906409d7748dec3193768c58739b26e45).

## Namespace prefixes are optional as of v2.6

In D3 2.5 and earlier, you’d append elements with their namespaces, like so:

{% highlight js %}
var vis = d3.select("body")
    .append("svg:svg")
    .append("svg:g")
    .append("svg:rect")
    // ...
{% endhighlight %}

But as of D3 2.6, you don’t need to specify the namespace prefix. To my understanding, this is true for the default rendering method, which is <abbr title="Scalable Vector Graphics">SVG</svg>.

{% highlight js %}
var vis = d3.select("body")
    .append("svg")
    .append("g")
    .append("rect")
    // ... 
{% endhighlight %}

This problem is compounded by a mixture of examples found on the web, especially examples like [this histogram](http://bl.ocks.org/993912) which statically link to an old version of D3 and do use the prefixes. If you take that source and try to modify it with code from the mainline [D3 examples](https://github.com/mbostock/d3/tree/master/examples), you will end up with a confusingly failsome situation.

## Symptoms

If you’re following examples on the web but you’re using an older version of D3, the problem manifests itself as 0×0 “invisible” elements in your browser. They show up in web inspector and firebug, but they don’t render in your viewport. More confusingly, if you’ve assigned width/height attributes, inspecting the element will highlight a region in your browser’s viewport, even though nothing gets painted inside.

## Solution

Use a newer D3, or make sure to use namespace prefixes if you’re using pre-2.6 D3.

With both kinds of code in the wild, there's no good way to publicize this pitfall everywhere it could be encountered. It isn't really a backwards-incompatible change, as the old syntax still works. A project changelog highlighting this sort of major feature addition would be helpful, but it’s the kind of remedy which only helps *after* you’ve stepped in the poop and gone looking for solutions. Unfortunately, this post is that kind of remedy too.

Hopefully Google almighty will soon work its indexing magic so others can experience the cathartic bliss that comes with understanding why something is broken.
