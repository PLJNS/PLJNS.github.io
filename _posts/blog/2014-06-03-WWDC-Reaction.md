---
layout: post
title: "WWDC2014 Reaction"
categories:
- blog
---

Apple's Worldwide Developer Conference may be one of the most misunderstood conferences held by
a public-facing company. The relationship between what the event *is* and how the event is
*perceived* makes for frustrating comment sections on tech blogs, news outlets, and developer
communities. Well, more so the former and less so the latter.

The WWDC is an annual conference Apple holds to tempt developers into developing on their platforms
with their technologies. The bulk of what the conference *is* are the workshops and presentations
on software engineering. Conversely, the bulk of how the conference is *perceived* is the conferences
keynote presentation, of which the WWDC has become nearly synonymous with.

As a recovering fanboy and a budding developer, I offer this post to interpret what happened at the
event and specify what I am most excited about. 

First, I will outline some of my thoughts about the changes to OS X. This is followed by the changes
to iOS. Interestingly, however, the best of the WWDC announcement did not exist on each platform alone,
but rather in the interplay between the platforms. That is, it is not in any single new software feature,
but in the single experience that Apple is cultivating across its different products. So that's what I'll
cover after OS X and iOS. Finally, I will cover some of the news that Apple had for developers.

### OS X Yosemite

Apple opened the event with the updates to its desktop operating system, OS X. Aside from bumping
the version number from 10.9 to 10.10, Apple has brought a new look, some new core features, an
update to Spotlight (hit Cmd-Space to find out what that is), some radical Safari changes, a few
convenient Mail changes, but most importantly, I think, an revamp of iCloud's capabilities.

The new look is trivially a big part of how Apple's operating system is perceived but more
crucially a big part of how the event is perceived. So what specifically has changed and
what does it have to do with the perception of Apple and the WWDC? The changes are:

-   Flat design, (fewer color gradients) 
-   iOS-style translucency and Gaussian blurs
-   Helvetica Neue replaces Lucida Grande

These changes are all in the right direction for a modern look for Apple's desktop
OS, says the fanbody devil sitting on my left shoulder, but it is not really why the WWDC's
annoucements for OS X are exciting, says the developer angel on my right shoulder. 

Before what's exciting, an interesting pattern emerges from noticing that the new Spotlight
*sherlocks* a smart search tool known as Alfred. (Sherlocking is when third-party developers 
ship a particular feature first and Apple subsequently implement and release it themselves.)

The feature that matters the most announced yesterday is called iCloud Drive. If Spotlight sherlocks
Alfred, then iCloud Drive sherlocks Dropbox *and* Google Drive.
Contrary to the per-app file management strategy that 
Apple has been taking, iCloud has been opened up to allow you to manage everything in 
iCloud via Finder. This includes everything that your iOS apps store there, anything you want to 
share between all your Macs, and anything you'd like to send to your apps. 

Interestingly, this the latest in a series of features which could be uncharitably characterized
as exemplify the Steve Jobs quote which was aptly stolen from Picasso, that "Good artists copy,
great artists steal." 
[As Gizmodo point out](http://www.gizmodo.com.au/2014/06/did-apple-sherlock-blackberry-in-ios-8/), 
Apple have done this before with Instapaper and Safari Reading List.

One of the reasons that iCloud Drive is so important going forward is that I have heard many times,
take the general sentiment to be, and it be the case that Apple's web services are underpowered.
Compare iCloud's present collaboration and file-sharing functionality to Dropbox and Google.
Dropbox is the *de facto* standard for sharing filesystems, and Google Drive is the *de facto* 
standard for sharing and collaborating on files. 

With iCloud Drive, Apple is competitively placed to implicitly takeover both of these use 
cases on Macs and iOS devices. Google Drive and Dropbox are software additions to any machine,
require separate accounts and configuration, etc. Conversely, every new Mac shipped and all
Mac OS X upgrades will feature this tool by default, and with the advent of BYOD, Apple is
positioned to be the default. 

This is not the only place that Apple continues to wage its "thermonuclear war" on its
old friend, the updates to Safari place Wikipedia results and other items before conventional
web search autocomplete.

**tl;dr** What you should expect is that in the Fall, a visual overhaul of your Mac will
be released. It will feature a number of improvements, the biggest of which is iCloud Drive,
which will give you an OS integrated Dropbox and Google Drive feature set.

From a developer's technical point-of-view, the improvements to OS X are tepid at best,
heated by the monumental improvement to Apple's web services. From a fanboy's point-of-view,
I cannot wait to have the visual updates to OS X light up my Retina display.

### iOS 8

Contrary to the glaring visual changes to OS X, the changes to iOS are not visual at all.
What iOS 8 is to iOS 7 is what Mountain Lion is to Lion: a subtle but global fleshing out
of the functionality. Arguably, many of the features which iOS 8 brings, like improvements
to Siri, a predictive keyboard, interactive notifications, and a better photo management
system, should have come to iOS a while ago. What I mean is that competitors have shipped
these items before Apple has, much before. The case-and-point is how Android-y the
predictive keyboard is and Google's ever better Siri clone. 

One of the most surprising announcements that Apple made was that it is allowing third-party
developers to create and ship software keyboards to iOS devices. The rationale for disallowing
the practice has historically been than it opens up a number of security and experience 
issues. Specifically, if a developer has access to your keyboard, and developer has access
to everything you type, and perhaps you type sensitive or personal information. Further,
should you pick up any iOS device and are accustomed to the platform, you will instantly
be able to begin typing. Some software keyboards are *very* different from conventional
software and hardware keyboards, including everything from swiping to drawing.

In similar vein, iOS 8 gives developers a way to give users a safe means to have their
apps interact with one another. For instance, if you are creating a social network and
want users on iOS to have your share sheet presented in the OS when a user wants to share,
iOS 8 gives developers a way to do this. Or if Instagram want to allow other photo applications
to use its filters, iOS 8 gives Instagram's developers a way to offer that service. 
The reason this is similar is because this has been disallowed by Apple in the past
for security reasons: apps are sandboxed to their own files to protect the user's other files.

One of the reasons apps have been so successful is that there is little to no risk of any app 
changing your phone in a way that a Windows XP malware might. The types of permissions 
that Windows XP granted to executables was much greater than the permissions an 
iOS app has, which is why a user can be quite careless about what they install in a 
manner that proved to be quite catastrophic on
more lenient systems.

The common denominator of the additions of third-party keyboards and app interactivity
is that it is an anachronistic "highly controlled openness." What I mean by this is 
twofold:

1. Yes, you can now have app's interact and change your default keyboard.
2. No, potential attacks are not possible in the way they are on competing products.

Specifically, the reason that this approach is not prone to malware is that
keyboard are not given default access to the network, for instance. If a keyboard
cannot connect to the internet, a sketchy company cannot make a key-logger without
your permission. Further, the inter-app communication *is* a form of openness in that
it allows developers to have deeper access to the interactions outside of their
application, but it protects the user by sandboxing the inter-app communication. 

I take this to be how inter-app communication and third-party keyboards "should have"
been done in that it is the sleekest and safest way it has been implemented so far.
I hope that the common denominator between these two new features and iCloud Drive
is this: When I use iCloud Drive, I hope it has the feeling of being late to the
party, but being the best dressed.

Apple takes further aim at existing app developers of the more ephemeral social networks which have been
enabled by more powerful devices and people's desire to take increasingly complex
selfies, namely, Snapchat's feature of being able to quick send video and images
to another on a timer. In iOS 8, the Messages app allows you to send video, audio,
picture, and location to others.

Another strategy Apple is taking with iOS 8 is defining central location for
existing but disparate services. The health quantification apps are all over the
place: lots of hardware, lots of software, and little communication or unified direction.
With iOS 8's HealtKit and Health app, Apple has defined a way (HealthKit) for all of these 
developers and manufacturers to centralize the information and services they provide into
a single place (Health app). 

Apple mirrors this approach for home automation products and services. With iOS 8's
HomeKit and Siri, Apple has defined a way (HomeKit) for all these developers and manufacturers
to centralize the informations and services they provide into a single place (Siri). 
How does Siri control your home? Well, you need only ask her. When you return home from a long day,
you need simply groan into your phone "I'm going to bed." and Siri will know to lock you garage,
dim your lights, lock the door, and check that the dog has enough water.

**tl;dr** Apple's iOS 8 will give you things you've wanted for a long time: interactive notifications,
third-party keyboards, family iTunes accounts, improved photo management, improved Siri,
and inter-app communication. It will also give you features you didn't know you wanted,
but come to think of it, it *is* the future: centralized and powerful health quantification and
centralized and intuitive home automation. All of these services share a few common 
and very Apple-y common denominators: 

1. The features take existing services and integrate them at the OS level,
2. The features are late but are much better in virtue of being integrated, 
3. The features are better in part because of how secure they are.

From a developer's technical point-of-view, the updates that Apple is bringing to
iOS are monumental, especially when taken in tandem with the framework updates
Apple is making. From a fanboy's point of view, the updates to iOS are tepid at best,
not only are there no exciting visual changes, but the most of the added functionality
is long overdue.

### iCloud and Continuity 

If OS X is the Father which was there at the beginning and iOS is the Son that redeemed
Apple as a company, then iCloud and Continuity is the Holy Ghost, the ever-present and all-knowing
space between your phone, your tablet, and you computer. It is in this space that the WWDC was
most exciting to me as a user. On this front, Apple announced four new features:

1.  Handoff,
2.  Airdrop between platforms,
3.  Instant hotspot, and
4.  SMS and phones calls on all platforms.

Handoff is a feature that allows you to *begin* working on an email or a document on any
one of your devices, and subsequently *continue* working on that email or document on *any
other* device *instantly*. For instance, if you are working in Pages on a blog post and you
want to move from your desk with a desktop computer to the conference room with your tablet,
when you open your tablet you will have an indicator at the bottom of the screen to open 
up and continue work on that document. For far too long have I carefully selected which device
I choose to work on a given task on because of limitations and typing and portability, and
I am very pleased that I am now empowered to just use whatever it is I am presently on without
the need to awkwardly transfer files.

However, if I do want a one-time transfer of a file from my Mac to my iDevice, the updated
AirDrop allows me to do that. This is going to be very convenient for when I, as I have found
myself, need to transfer a file on my phone to someone who is working on their Mac or vice-versa.
This is a much requested and workhorse feature whose utility should be evident.
Much in the same boat is Apple's now easier Instant Hotspot feature, which allows me to use
my phone's cellular data as the Internet for my Mac, which is another hugely convenient
addition.

The feature I am *most* excited to get my hands on as a user, however, is that no longer
do I have to use my phone exclusively to make phone calls or use SMS. When I pair my
phone with my computer and my tablet, now I can use those protocols from any of my 
devices. *Hallelujah*. 

But not only is this interesting from a user point-of-view, but from a strategic point-of-view.
With Facetime and iMessage, Apple entered the telecommunications market subversively. 
Facetime Audio and iMessage are barely noticeable from the standpoint of the user, they
are simply a more convenient and feature-rich version of what telecommunications companies
already offer them. In fact, many other companies offer instant messaging and VoIP.
What's different about Facetime and iMessage is that they are seamlessly integrated into
your existing SMS and telephone, technologies that have not much changed in the last
one hundred years. By expanding its influence to *all* SMS and phone calls, Apple is 
positioning itself to quietly topple public-facing telecommunications companies from 
bottom-up.

**tl;dr** If you own all three or any two of the Apple's product categories, the
intercommunication and shared experience are better than they have ever been or 
are anywhere else. Where Google's Android is ubiquitous and Microsoft's Windows is homogenous, 
Apple's OS X and iOS are seamless. More simply, you'll be able to share documents, share your 4G,
take phone calls on any device, and send/receive SMS on any device.

The user's perspective transcends the developer/fanboy divide, as it will help me do
all of my tasks better *and* allows me to use my favorite devices more.

### `DEV`

Apple announced a new programming language to replace Objective-C, and that language
is called Swift. The features presented in the keynote were very, very exciting, and
most of all its "Playground" feature. What Playground seems to be is that when you are
writing code in Xcode and Swift using Playground, when your code compiles Xcode performs
some introspection and analysis on it to display on the right hand side a visualization of
what your code does. So, for instance, if I write a loop which runs 100 times and moves
a UI element from the bottom of the screen to the top, Playground will show that it runs
100 times (if I coded it correctly) and show me the UI element's movement right from
Xcode. 

I see Playground as being one of the first seriously compelling reasons to move from
a terminal based text editor to an IDE. Of course there are others, IDEs make it easier
to use debugging tools and have less of a learning curve. But I have not known a task
that was *impossible* with my favored `vim` until this Playground feature was demoed.

The fanboy in me obviously doesn't care about a new programming language, but you may
be surprised to learn that the developer in me in strangely apathetic as well. 
Until some more information is released and I get the opportunity to try writing
an app in Swift for the first time, I reserve my judgement about it. Why? Because,
frankly, learning a programming language, and especially learning it well and fully,
is *very hard*. Furthermore, Swift, like Objective-C, is a platform specific language.
Of course you *can* use Objective-C with GCC on any machine, but it is Cocoa that really
makes Objective-C a pleasure to develop in.

What is revolutionary from a development point-of-view, however, is Apple's announcement
of "CloudKit." CloudKit is an API a developer can use to securely store and efficiently
retrieve cloud-based data as thought it were in a local database. Apps have become
much more stack-heavy in recent years: When you develop an application for an Apple
product these days, you are not just developing for one device but for the entire 
ecosystem. It used to be that an iPhone app would mostly just run on the intended
device *and maybe eventually* the Web. Now, application development requires a back-end
for authentication, accounts, in-app purchases, and analytics. This is a massive undertaking
for a lone developer looking to publish their idea. CloudKit allows me to do what I do well,
compiled, on-device application development, even more powerfully because I can define the
server-side logic on device and off-shore the task of running and maintaining to Apple's servers. 
Revolutionary.



