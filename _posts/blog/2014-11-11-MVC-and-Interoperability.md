---
layout: post
title: "Developer Journal: MVC and Interoperability"
subtitle: Architecting applications in the most cross-compatible way
categories:
- blog
---

The desire for code re-use is a strong one among considerations
of how to design a program or application. This competes with
the desire to implement applications in their native, and oftentimes
proprietary, framework.

Arguably the most important part of a mobile application to be
developed natively is the view code. Non-native views on
any sufficiently complex data-centered app are almost always
immediately identified by users: web views and non-standard
behavior almost always give it away.
Furthermore, perhaps the least important part of an application
to be native is the model. The storing, manipulation, and retrieval
of data is oftentimes very similar across languages and frameworks:
a linked-list is a linked-list no matter what language it's in.

Perhaps we can use this dichotomy to best satisfy the competing
desires of code re-use and native implementations: keep your
views and controllers in native code, but implement your data
model in shared code.
Specifically, I'm wondering if I can move an application's
model to C++ on iOS, Android, and Windows Phone and only
implement views and minimal controllers in native code.

In fact, ideally, all data-related tasks would be handy to have
in shared code: anything involving databases, making requests to
servers, and parsing responses are the taks which come to my
mind.
I think that in order to achieve this, I'm going to need to
compile a framework for manipulating a database, a framework for
making network connections, and a way to have native code
request and receive data. 

I think a design like this at least works, but it could even be
desirable. Maybe the best way for me to find out would be to
try it.