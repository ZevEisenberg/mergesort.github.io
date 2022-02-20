---
layout: post
title: The Best Twitter Bio? The Humble Tweet
tags: [industry, featured]
---

Tell me who you are in 160 characters. I'll wait while you try and achieve the level of nuance necessary for the task. This constraint is why you end up with generic Twitter bios that don't tell you much about someone and all look like:

> Father, cyclist, biz-dev, and fighting every day for the Quebec sovereignty movement. Working on saving democracy @Meta, ex-Palantir, ex-Accenture, ex of my ex.

Kinda hard to stand out, right? The inability to differentiate yourself on a platform built upon self-expression has always felt unexpected to me, so I started to look for alternative means of expressing who I am. The most common approach to gain additional room for expression is to use Twitter's Website field, linking out to a more information-rich bio. But that jump to the web is an opportunity to lose focus, especially in a world where nobody has the attention span to read (or leave Twitter). There are even solutions like [Linktree](http://linktr.ee) that build upon the link to link to a link of links, letting those links speak for you.

There are plenty of hacks one can imagine using, more advanced users have taken to pinning an “intro thread”, but what I was looking for was an option that would let me be more expressive than a bio, felt eloquent, and was native to Twitter. That's when I remembered the humble Twitter carousel. You may have seen carousels serving you ads for apps or services that everyone is excited about like… VMWare Cloud.

![An image displaying a carousel ad for VMWare Cloud]({{ site.url }}/assets/img/vmware-twitter-carousel.jpg)

But did you know that Twitter's advertiser tools are available to everyone, without having to pay a penny?[^1] That's right, you a regular Twitter user can have the same capabilities as a company that pays Twitter millions of dollars per year. I'm going to show you how to take advantage of them so you can stand out just like household brands such as Disney, Nike, and of course… VMWare.

### Who's *That* Handsome Guy? About Me

<blockquote class="twitter-tweet" data-dnt="true"><p lang="en" dir="ltr">About Me</p>&mdash; ✨  Joe Fabisevich  ✨ (@mergesort) <a href="https://twitter.com/mergesort/status/1495178694553444355?ref_src=twsrc%5Etfw">February 19, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

I've always debated whether my bio should link to my [home page](https://fabisevi.ch/), my [About Me page](https://fabisevi.ch/about), or the [best posts](https://www.fabisevi.ch/tag/featured-posts/) I've written. Thanks to the carousel I no longer have to choose, and I'm able to put all three front and center. The flexibility of having six links means I can also guide people to the [office hours](https://redpanda.best/office-hours) I host, and have room to spare for another link or two.[^2] As importantly as taking the time to construct the tweet is remembering to pin it, that way anyone who comes to my Twitter account has this information visible immediately.

<blockquote class="twitter-tweet" data-dnt="true"><p lang="en" dir="ltr">Do you love red pandas? Love apps? Find out more about what we do!</p>&mdash; The Red Panda Club (@redpandaclub) <a href="https://twitter.com/redpandaclub/status/1495170167940292614?ref_src=twsrc%5Etfw">February 19, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

A brand can get really creative by linking to their homepage, their support page[^3], FAQs, App Store apps, and a whole lot more. The carousel is also a medium to play with, you can use custom artwork to show off your brand's style, which in my case is playful and silly. I created a tweet carousel for my indie development company [Red Panda Club](https://www.redpanda.club) as a proof of concept, and pinned it to the top of the [@redpandaclub](https://twitter.com/redpandaclub) Twitter account.

### Building Your Carousel

The process for building your own Twitter carousel is hidden away, but surprisingly easy.

1. Head over to **ads.twitter.com** and look in the navigation bar for a menu titled **Creatives**. Under Creatives you'll find a menu item titled **Tweet Composer**, this is unsurprisingly what you'll want to compose tweets. The URL will look something like ads.twitter.com/composer/XXXXX/carousel, where the XXXXX will be a random set of letters and numbers.

![An image showing you where to find the tweet composer]({{ site.url }}/assets/img/twitter-tweets-composer.jpg)

You may run into various popups asking for more information, feel free to ignore ‘em! The only popup you’ll see that you have to fill out is one asking you for your credit card information. [^1]

![An image of a popup telling you to add information for your business]({{ site.url }}/assets/img/twitter-business-popup.jpg)

And that's actually it, there's no real step 2 beyond composing your tweet. But to save you some time I'll mention a few things that may seem unintuitive.

A) Your first step for customizing the carousel is to add media. You can't start creating a card by updating the website destination; that will only appear after you've chosen media for your carousel.

B) Website cards can customize the text that displays under a card's image, but app cards always display the app name and app category under the image.

C) You’ll be asked to choose an app carousel or a web carousel, but don’t let that think you can't make one that mixes the two together.  To do this you'll need to choose a website carousel and for any app you want to add you'll use your app's App Store or Google Play URL and manually upload your app's icon.

D) The Tweet Composer will default to making your tweet Promoted Only. If you want the composed tweet to show up on your profile timeline remember to uncheck the Promoted Only checkbox. It's worth noting that a Promoted Tweet is a real tweet, but you’ll only be able to find the tweet’s URL in the Twitter Ads dashboard.

E) Cards do not render in third-party clients[^4], so if that's important to you I recommend including text and links in the body of the tweet. It doesn't look as good in native Twitter clients so it's your choice whether to prioritize this or not. 

Now that you know how to build a fun carousel, I'd love to see you get creative. I can't wait to see what kind you come up with. 🎠

[^1]: **You really don't have to pay Twitter anything** to use the tools but you will be asked to add a credit card.

[^2]: I expect these links to change so I'm not particularly attached to them, and if I ever do change them I can always post an updated tweet. Alternatively using a link shortener is a good strategy for not having to change the underlying data.

[^3]: Twitter doesn't let website carousels link to custom URL schemes so I got a little creative with my support link. Using my [redpanda.best](https://redpanda.best) URL shortener I linked to a page who's contents contain `<body onload="javascript: window.location.href='mailto:abc@mywebsite.com';">`, to work around the fact you can't use a `mailto:` URL.

[^4]: Unfortunately the underlying cards these carousels are built on aren’t exposed in the [v2](https://developer.twitter.com/en/support/twitter-api/v2) third-party API tweet payload, so they can’t be rendered in them.