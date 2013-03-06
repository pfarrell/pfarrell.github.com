---
layout: post
title: "Framework Creep"
---
### _tldr;_
This is probably just a restatement of [YAGNI](http://en.wikipedia.org/wiki/You_aren't_gonna_need_it).

There are ways to plan for the future without trying to solve non-existant problems.

| Bad | Good |
|---|---|
|Factories that produce instances of a single type|Create and code to an interface|
|Lots of code (either in lines or executions) moving data into and out of your object model|Deocorate the natural structures your code receives|
|complicated custom sorting code for small data sets|Using out of the box sorts until it's a hotspot|
|![bad-inherit](/images/bad_inherit.png)|Shallow inheritance trees

Software is meant to be molded.  Good practices produce software that is easily molded.  Good software grows because it has solved real problems.  Frameworks do not solve problems.  Well... [unless](http://rubyonrails.org) [they](http://hibernate.org/) [do](http://angularjs.org/).  But those "real" frameworks made their bones as solutions extracted from smaller successful projects.  Projects that solved real problems.

If you're codebase becomes successful, there will be major refactoring to bring it to "public" 1.0.  Nothing you can do now will prevent that.  All you can do is prevent your system from being useful, today.
