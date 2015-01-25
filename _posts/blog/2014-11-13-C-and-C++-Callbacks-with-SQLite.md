---
layout: post
title: "C and C++ Callbacks with SQLite"
icon: code
categories:
- blog
preview: >
         Etiam porta <em>sem malesuada magna</em> mollis euismod. 
         Cras mattis consectetur purus sit amet fermentum. 
         Aenean lacinia bibendum nulla sed consectetur.
---

Everything is data. Occasionally, when programming day-to-day objects
and functions, you get a reminder that everything from the keys you
press to the code it makes to the bits it reads is data.

But enough, say you want to use C++ with SQLite in a sane,
object-oriented way. More specifically, you want to use `sqlite3_exec`
to execute a SQL query. Here's an example:

	int rc = sqlite3_exec(db, sql, callback, data, &errMsg);

What is each one of these parameters? The first, `db`, is your
opened database, `sql` is a `const char *` query you want to run,
`callback` is a static function pointer, data is a peice of data
you want to send to `callback`, and `errMsg` is what it sounds like.
Okay, all's well, lets define that callback.

	static int callback(void *param, int argc, char **argv, char **azColName)
	{
	    return 0;
	}

*Damnit*. This is going to be called once for every row, I don't know when
it's going to end, *and* it's `static`, throwing any hope for object-orientation
out the window. 

Or does it? Switch gears for a moment: What's one of the hallmarks of object-oriented
programming? I'm talking about the keyword `this` or `self`. What `this` is is
difficult to describe to others because you'll often find yourself saying something like,
"`this` is this, like you know, this is `this`". But `this` can be thought of as
a hidden parameter passed along with every message sent to an object which can
access the object that the message was sent to.

Well if `this` is what we're after, `this` is a hidden parameter, and
we've got a `void *` we can put whatever we want in, how about we just
reconstruct our instance of an object using C++ casting?

First, make your request:

	char* customer::getPerson(int id)
	{
	    ...
	    rc = sqlite3_exec(db, sql, callback, this, &errMsg);
	    ...
	}

Then, define your C callback with C++ casting to turn `person` into `this`:

	static int callback(void *param, int argc, char **argv, char **azColName)
	{
	    Person * person = reinterpret_cast<Person *>(param);
	    return person->cppCallback(argc, argv, azColName);
	}

Finally, profit:

	int Person::cppCallback(int argc, char **argv, char **azColName)
	{
	    ...
	}

Thanks to [this](http://stackoverflow.com/questions/14437433/proper-use-of-callback-function-of-sqlite3-in-c)
StackOverflow post for the insight.