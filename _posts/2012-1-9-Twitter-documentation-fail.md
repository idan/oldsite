---
layout: post
title: Twitter’s poor API documentation practices
---

I heart Twitter to itty bitty pieces, but today I was again dumbfounded at the scope and severity of fail I encountered in their documentation. Of all the large product API’s I consume regularly, Twitter’s is the one I’ve had the worst experience with. There’s nothing severely broken *per se*, but the experience has a high incidence of sharp edges and unpleasant surprises—all of which are completely avoidable with good documentation.

I’m relating my experience in the hopes that somebody on the API team makes substantive changes to their documentation process.


## retweet_count

`statuses/user_timeline` returns a series of tweets. In each of these tweets, one of the fields is `retweet_count`.

### Failure #1
Nowhere is it documented that this value is capped at 100. Nowhere is there an example showing that this might be the case.

### Failure #2
From the examples, it is implied that the value is always an integer. None of the example results show anything but an integer.

### Failure #3
The fact that I must guess what potential datatypes a field may return is a failure of documentation unto itself.

### Failure #4
Nowhere is it documented that if this value exceeds 100, it suddenly becomes a non-integral string... wait for it... “100+”. Any code that I wrote under the (mistaken) impression that I’d be dealing with integers will break when it first encounters a tweet with more than 100 retweets.

## Documentation, not engineering

Note that I’m not really complaining that the value _is_ capped at 100. It’s a shame, but there are engineering constraints which factor into this decision. I mean, it’s not like they arbitrarily cut off a useful datapoint at 100, right? Right?

Worse, I can’t understand how any engineer thought the “100+” solution was a good idea, but forget that for a second too.

I cannot fathom _any_ reason why the above documentation failures exist. This isn’t the first time I’ve eaten dirt with some poorly-documented behavior in the Twitter API, but this is certainly a severe example.

Twitter, I love your product, but why do things have to be this way? Good documentation isn’t easy, but it isn’t a trip to the moon either. The solution isn’t to fix my bug. The solution is to change your documentation practices so no bugs like this can exist.

I can tolerate engineering limitations, even arbitrary ones! I may grumble, but accurate documentation is far more valuable. It enables me to write correct code without excessive defensive checks to protect me from you. They enable me, *your audience for this part of your product*, to trust you.

Make this somebody’s job. Measure what works and what doesn’t by doing usability studies—it’s really easy! Get developers in a controlled setting and ask them to write code that consumes an endpoint in your API. Run that code against a large, varied slice of data. If there are failures, figure out what part of your documentation is responsible and write better documentation. Rinse and repeat for every endpoint in your API.

Love,

Me