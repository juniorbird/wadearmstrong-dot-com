---
title: "Console Log vs. Breakpoint"
date: 2020-02-11T14:04:43-08:00
draft: false
categories: ["coding"]
images: ["/blog/console_log_vs_breakpoint/MemoryNetwork.svg"]
summary: "I `console.log` a lot. And I know that's not always classy. Folks look at me crosswise because I don't open up a debugger. But here's the thing: it's not just that I'm old-fashioned; there's acutally something about `console.log`ging that's different &mdash; and sometimes better &mdash; than using a debugger."
---
I `console.log` a lot. And I know that's not always classy. Folks look at me crosswise because I don't open up a debugger &mdash; and all Web browsers have quite good debuggers these days[^1] &mdash; but here's the thing: it's not just that I'm old-fashioned (although I am, and I certainly started developing well before decent in-browser debuggers), there's acutally something about `console.log`ging (or `fmt.println`ing or `echo`ing) that's different than using a debugger. Logging out your code's state is debugging _from a specific perspective_; using your browser debugger actually _moves you to a different perspective_.

h3. How Perspectives Work

In the social sciences[^2], there's this concept of "framing." A "frame" is a filter, more or less, through which we all take in and analyze information. Some filters are basic and come from our experiences in nature &mdash; "Mom is good, this smells like Mom, it must be good" &mdash; but most are socially-constructed &mdash; "Eating fat makes me fat, so I'll choose the 90% lean ground beef over the 10% fat ground beef."[^3]

While the filter itself is an abstract entity, neuropsychologists have considerable evidence that something much like frames actually exists in your brain. The [Spreading Activation Theory](https://www.researchgate.net/publication/200045115_A_Spreading_Activation_Theory_of_Semantic_Processing) holds that the likelihood an individual retrieves a memory is directly proportional to the strength of the connections to that memory. Think of memory like a graph, with nodes connected in the center as a crazy-quilt, but out at the edges as trees, with memory retrieval starting at the center. Each node on the graph is connected more strongly or more weakly to its neighbors; heck, think of components of memory as having PageRank. To get to a node on the edge, you need the path from the center to that edge to have sufficient strength throughout to get you there; but, once far enough down a path, the connections from a given node in that path to a node in a completely different path are much weaker than the within-path connections.

![A graph, showing a few childhood memories networked together, with GI Joe's Lt. Falcon way out on his own connected only to GI Joe, while other nodes are linked to each other](/blog/console_log_vs_breakpoint/MemoryNetwork.svg)

Here's a trivial example: my childhood memories. Look how many paths there are to get from my happy memories of playing to my traumatic memory of crashing my bike. But you have to activate a specific path to get to my memories of my [GI Joe Lt. Falcon](https://gijoe.fandom.com/wiki/Lt._Falcon) action figure.

What that means for all of us is that, when we get far enough down our semantic network, only one frame is available to us; others are just too weakly-connected to flip over to, at least not without significant mental effort. This happened to me in a job interview just a few months ago &mdash; I was working on GDPR compliance at my old job, so was thinking about privacy of PII. My interviewer asked me how to keep a variable's value private in Javascript in the browser. The correct answer was "using a closure," but, focused on the GDPR frame, I said something like "once you send it to the browser, man, everyone can see it! It's the wild west out there! There's no privacy."[^4] The concept of "private" was framed in my mind as "information," not "variable private to a given function or method," so I missed it.

This is all a long way of saying that the frame you use to filter information from the world around you absolutely neurologically limits your ability to think about that information in a different way. But, when we're stuck on a programming (or, really, any life) challenge, thinking about the problem in a different way is essential to moving forward.

h3. The Debugger Perspective

It's kind of obvious where I'm going here: using a debugger gives you a specific frame through which you look at the world. To be more exact, it gives you the frame of looking at the code from the outside.

Which is great! This allows us all to use debuggers to understand code we have no business understanding. Third-party library? No problem! Spooky behavior potentially caused by the platform not adhering to the spec? I can figure that out!

But it is that divorced-from-the-source-code frame, and it's hard to get back into the code directly from the debugger. Not physically, since usually there's a line number or even a link to the line in your IDE; but in your mental model. You need to store lots of state in your head: information of where you're looking in your code; what drives the execution of that code; which inputs you care about; and more.

Debugging is thus great if you have something behaving wrong and you don't know why. You can use its frame to evacuate presuppositions from your head and look fresh from the outside.

h3. The Logging Perspective

But, look, sometimes everything is going _great_. You're writing code, you're on a roll, but you need to know: what is the shape of this data here? Do these two lines really execute out-of-order? We fall into that branch, right?

Then your perspective is inside the code. And what works well in that frame? Well, logging out the data that you need. Yeah, in a lot of cases you can set a breakpoint and watch what's going on around that, but the point is that you don't need a generic act that might give you all different kinds of information: you need to specifically get the piece of data you want.

Logging gives you complete control of that. It defines the frame as "I'm here, what's the situation with _<x thing of interest>_?"

Logging is also great when you're refactoring. Want to make sure you're still executing a step in some complex branching process that all flows back together in the end? Well, step through dozens of operations... or just put one `console.log('in interestingFunction()')` in the right place. Doesn't matter how you change your branching structure, you don't have to keep track of where you want to set the breakpoint, you just get the informtion you need, when it's available.

h3. Can't We All Just Get Along?

I may be a bad developer, but it's not because I `console.log()` things a lot. You may be a good developer, but it's not because you're better with a debugger than I am.[^5]

But one part of what makes us good developers is our ability to look at problems in effective ways. So keep in mind the ways that you can use these two different debugging techniques to frame your approach to the problem in different ways. That gives you one more tool in your belt.

[1]: Rest _not_ in peace, IE11 Developer Tools!
[2]: Developers should spend a lot more time reading social sciences
[3]: Yes, the frame is tricking the speaker there. Frames do that a _lot_
[4]: And yet, they hired me
[5]: I use my debugger all the time, so you might not be
