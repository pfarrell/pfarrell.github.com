---
layout: post
title: "Building too Much"
tldr: Build the smallest, least complex thing that solves your problem.
---
This is the story of the time I learned about scope creep.  

The company was a collection of autonomous portals in different states.  Each portal had a billing system, reporting to corporate at month's end in roughly similar fashions.  

Corporate wanted better visibility into day to day financials of each of the portals. 

No one, but Corporate, wanted the new billing system.

We were doomed from the start.

Among my duties, I was tasked with designing and implementing a testing framework.  It would handle unit testing, release testing, integration testing, load testing.  It was my first major greenfield project

After lots of contemplation, I came up with the most awesome design proposal I could muster.  I didn't know the word, but I wanted to build an testing [DSL](http://en.wikipedia.org/wiki/Domain-specific_language)

I proposed to create a higher level language, in XML (this was 2004, after all), that would activate certain functions to produce tests.  Probably be really easy.

My manager loved it, but wanted to know how would we handle

  *  establishing context for the tests?  (well... XML to call into java.util.collections)
  *  formatting the result (I guess more XML to call into java.text)
  *  adding things at runtime (hmm... XML to call into java.lang.reflect)
  *  multiple conditionals on outputs (more xml...)

__Wait a minute!!__

I can just write simple functions that take my XML structures and reflect them out to java objects and methods

I can just write Java in XML and use my parser to generate the Java.

Oh YEAH!!! Now I'm thinking like a ___[real programmer](http://catb.org/jargon/html/story-of-mel.html)___.  I explained my plan to my manager.

There's something about explaining to others that helps you hear it anew.


> I can write Java... 
> format it in XML...
> and use a parser...
> [which I have to write]...
> to generate...
>
>...Java

"Wait... Why am I not just writing Java?"  

I was going to got through a lot of crazy effort to create a custom version of Java that 

*  wouldn't be compiled
*  would be less efficient than Java code
*  would hide compiler bugs till runtime
*  would be maintained by me

The thing I learned that sticks with me to this day?  I constantly ask myself.  __"Are you building the smallest, least complex thing that solves your problem?"__  That lesson made the entire doomed affair worth it.

