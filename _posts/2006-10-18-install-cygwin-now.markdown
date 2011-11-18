---
layout: post
title: Windows Developer? Install Cygwin Now!
---

"There's something wrong with my computer." as the user points to the monitor.  

Anyone working with computers has had tech support experience (ad hoc or otherwise) and we've all seen this scenario.  We all silently laugh as our inner geek screms through his swollen adenoids, "hhnenk, you don't even know the monitor from the computer.  Geez."  I'm going to argue that there is a similar sickness infecting the ranks of the computer literate.  That disease is rigidity of thought.  Getting locked into the Windows mentality which can be summed as: "Here's how you have to do it."

The disease will have you locked into thinking what is on the screen is what you are interacting with.  I've been interviewing various developers recently who've all not been able to separate their programming from their programming environments.  I think a healthy dose of command line use reminds one that all these visual devices are mere analogies that allow our brains to get around what's going on inside the box.

If you've only worked on Windows computers then you should have yourself checked out for this disease periodically.  One vaccine is to force yourself to become acquainted with the power of the command line.  The best step I've found to accomplishing this is to install <a href="http://cygwin.com">Cygwin</a>, a <a href="http://www.gnu.org/software/bash/">bash</a> shell for the Windows operating system.  Think of this a the ability to replace cmd.exe with the more powerful tools available to our Unix counterparts.

1. Searching (and replacing)
You've got hundreds of text files that need to be searched for a specific term or worse, need to be changed.  You can try to use the broken Windows file search capabilities to locate the files then manually update them, or you can use a few quick commands in cygwin and let the computer do the work.
>**Example 1: The rebranding scenario**
replace the words "Cool Widgits" with "Our New Name.com" across all html files in the current directory and all subdirectories.
Here's one way to build the command:

Find all files in the current directory
> find . -type f  

Select only the files that end in "html"
> find . -type f | grep 'html$'

Now, run those html files through an inline replacement command using perl
> find . -type f | grep 'html$' | xargs perl -pi -e 's:Cool Widgits:Our New Name.com:g'

There.  You've just created a new one-off tool in a minute that would have required half a day in many other scenarios (or worse, you could have manually updated the files ;).  The best part is this.  If you've backed up the files, all your work is reproducible.  Your work is in the command, not the files themselves.  You've just taken a step into a larger world.
