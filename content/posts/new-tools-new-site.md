---
title: "New Tools, New Site"
date: 2019-07-22T20:15:07-07:00
draft: false
categories: ["Meta"]
summary: "I've had a lot of blogs over the years &mdash; starting in 1999, when I made my own CMS using Active Server Pages (well, all of a CMS except the \"edit post\" part, which turned out to be a problem), through the mid-2000s when I blogged through my business school experience, to personal blogging over the last few years. Blogging has always been great for me, because, to quote an old boss of mine, \"huh, you work out your thoughts by writing them down, don't you.\"<br /><br />Yep, that's why my name is all over the wiki at work. Sometimes I don't know how to do something or even what I think until I write it down (the same goes for code... the act of sitting in front of a text editor and starting my fingers across the keyboard makes code come faster than just thinking about it). I'm always better with a place to write..."
---
I've had a lot of blogs over the years &mdash; starting in 1999, when I made my own CMS using [Active Server Pages](https://riptutorial.com/asp-classic) (well, all of a CMS except the "edit post" part, which turned out to be a problem), through the mid-2000s when I blogged through my business school experience, to personal blogging over the last few years. Blogging has always been great for me, because, to quote an old boss of mine, "huh, you work out your thoughts by writing them down, don't you."

Yep, that's why my name is all over the wiki at work. Sometimes I don't know how to do something or even what I think until I write it down (the same goes for code... the act of sitting in front of a text editor and starting my fingers across the keyboard makes code come faster than just thinking about it). I'm always better with a place to write.


![a 1950s truck, in black-and-white](/blog/new_tools_new_site/truck_bw.jpg)

And I've got a lot to think about; everyone who makes the leap, or starts to, from individual contributor to management has a lot to think about. I've spent the last few years making great products, and now I get the chance to help others do the same. How do I make the most of who I am and what I care about, in this new context?

Of course, the challenge for a Web developer making a personal site is... how much do you want to show off with the site you make? Do you make something complex, filled with bells and whistles that show your skill and knowledge? That's a very valid approach, but it comes with a cost: creating the site is more complicated, and keeping it updated can be even more so. A simpler site can be easier-to-launch and be an easier place to create good content over time, but doesn't prove that one knows React or localstorage or coroutines.

One of my favorite engineering lessons is: make a system as complicated as it needs to be, but not any more. A fancy Vue/GraphQL/Rust site would be quite a great deal more complicated than it needs to be to introduce who I am and show off my writing.  I also write plenty of code at work, a lot of which you can see the results of online. And, as stated above, I do my thinking through writing. So I need a place to write, and I have a place to write cool code. Sorry I can't show it off --- we don't even use GitHub at work, so my profile there is very not-green --- but I do some cool stuff with [Preact](https://preactjs.com/) and PHP and even Go sometimes.

![A World War I fighter airplane's brushed aluminum open front cowl, showing the cylinders of a rotary engine, fronted by a wooden prop](/blog/new_tools_new_site/rotary-prop.jpg)

So: this is a place for me to write and think. How does it work?

I mentioned I write some Go. A top priority was to have a site I'd like working on, and that I was able to maintain fairly trivially. My first thought was building it out of Jekyll and GitHub pages, but here I have to admit that I know very little Ruby and quickly found that I'd have to learn a fair amount more to debug even the simple issues I ran into. Nothing against Ruby, which I know to be used by many quite fine and large sites, but it's just not an appealing language for me to learn from scratch right now. I'd rather learn something new like Elixir or expand my Go.

So what does "I like working on" mean? Ahh, requirements gathering. Here's what I came up with:

* Lets me write in Markdown, because I prefer that
* Themeable and extensible
* Written in a language I know well enough (or would like to know well enough) to troubleshoot
* Shows off my photos pretty (admittedly, this is more of a theme thing)
* Can host with GitHub Pages or something equivalently simple and free, since I pay for GitHub already (as well as other things; always pay for your software, it makes it continue to exist)

![Train tracks, splitting with a switch, close up](/blog/new_tools_new_site/tracks.jpg)

Pretty quickly, I discovered Hugo. It's a simple headless CMS that's quite customizable, and even has a simple path to deployment with GitHub + Netlify. The code in Hugo seems quite straightforward, with overriding templates, CSS, etc. just a matter of replacing a file, and a standardized way to add arbitrary content types, configuration values, etc., simply through... well, configuration.

The only downside that I can see is that Hugo uses something called [TOML](https://github.com/toml-lang/toml), a YAML-like language that's not YAML and also not JSON and also not XML and also... what I'm saying here is, I didn't need another simple configuration language. But that's my only complaint. (It looks like I could migrate to JSON if I really wanted to put in the effort, too.) Hugo's been simple to get set up and simple to get running.

What's funny is: 10-15 years ago I used [Movable Type](https://movabletype.org/), a perl-based CMS, to power blogs. It worked just like today's stylish modern CMSes, generating static pages that you could then serve quickly from any hosting account. MT was ultimately beaten in the marketplace by Wordpress, which dynamically built every page using PHP and MySQL, but which can be very, very slow without a caching layer on top of it. And, of course, caching layers like Varnish are just nice, fast static page servers, which is basically what MT was doing a decade or two ago. I even considered going back to my old friend Movable Type for this site, but, while my Perl is better than my Ruby, I've never loved the language.

![The five-bladed prop of a late-war Supermarine Spitfire, close-up](/blog/new_tools_new_site/spitfire-prop.jpg)

Anyway, I digress. But I *do* like Go, I like that it's a simple philosophically-consistent language. I like how it approaches types. I like reading it. I wish it supported more functional paradigms, or more fluent interfaces, but it's not bad to think in a different way after all the Javascript I write.

So: welcome to my site. It's got pretty pictures, which I'm proud of, and some posts, which I hope you'll like. It'll be a place for me to talk about, in public, the things that I only get to talk about to the engineers and EMs I work with. It'll be a place for me to get my ideas straight. Let me know if you enjoy it!