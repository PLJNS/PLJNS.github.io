---
layout: post
title: "Mastering the iOS Technical Interview"
subtitle: Some questions and answers to consider before the interview
icon: music
categories:
- blog
preview: >
         Etiam porta <em>sem malesuada magna</em> mollis euismod. 
         Cras mattis consectetur purus sit amet fermentum. 
         Aenean lacinia bibendum nulla sed consectetur.
---

### General Questions

-   **Can you describe your workflow when you work on creating an iOS app?**

    Sure. iOS is like any other platform or programming environment, and
    at the beginning, you need to collect a complete or good initial set
    of program requirements. After you and your coworkers or clients are
    happy with the requirements, it's time to start translating the
    program requirements into your software architecture. If dynamically
    updating content is a requirement, you're going to need a backend.
    If caching or manipulation of content is required, you're going to
    need a database, which will determine the structure and nature of
    your model. If a GUI is required, you're going to need to define
    your views. You wrap these components together with a controller,
    and assure that your naming convention is semantically similar to
    your problem domain, `downloadBusinessInformationFromBackend`,
    `storeBusinessInformationInBackground`,
    `updateViewForNewBusinessInformation`, etc.

-   **Are you familiar with CocoaPods? Can you explain what they are and
    how they work?**

    CocoaPods is a depedancy and package manager for Mac OS X and iOS,
    it downloads and integrates code from other projects, often through
    GitHub by use of specs, but it can also be used locally. The
    benefits of CocoaPods is that it encourages the strict seperation of
    dependancies and your programs source code, which can decouple your
    implementation from your dependencies. The downside of CocoaPods is
    perhaps that it itself is a dependancy on your project, that it
    makes a number of assumptions about how you want your project
    organized, and that the process of making a CocoaPod is likely more
    painful that it needs to be.

-   **In general, explain software licensing and how this applies to work
    we do.**

    Software licensing is the legal rules surrounding distribution, use,
    and modification of source code or executables. It applies to what
    we do because the license of dependancies often affects how you must
    license your software or parts of your software or modifications to
    the software.

-   **Describe your general testing practices when building an iOS app.**

    I take a broad approach to test practices for iOS. The model is best
    tested by unit testing, definining rigorouse and complete sets of
    inputs and expected outputs for your data model. This assures
    correctness at your app's most fundamental level. The controller is
    best tested with asserts to assure that they are used and modified
    in expected ways. Of course, you can place asserts in your model
    code too, but I think the unit tests are really doing the work
    there. The view code is best tested by QA testers, and like the
    model, it can contain asserts to assure good input, but ultimately
    the correctness of views is determined by good user experience and
    expected behavior.

-   **How can apps support other languages, date formats and currencies?**

    1.  The use of NSLocalizedString allows you to use a dictionary to
        define your applications strings, and switch what the dictionary
        returns based on the region.
    2.  The use of NSDateFormatter allows you to display dates in a
        user's expected format, and local.
    3.  The use of NSNumberFormatter will display currencies with their
        varying typographical conventions according the locale the user
        is in, Apple has graciously performed the heavy lifting here.

-   **What is Instruments and how is it useful?**

    Instruments is a application performance analyzer and visualizer for
    iOS and Mac OS X apps and it's built-in to Xcode. It allows you to
    profile for memory use and potential memory leaks.

    -   User events, such as keyboard keys pressed and mouse moves and
        clicks with exact time.
    -   CPU activity of processes and threads.
    -   Memory allocation and release, garbage collection and memory
        leaks.
    -   File reads, writes, locks.
    -   Network activity and traffic.
    -   Graphics and inner workings of OpenGL.

### iOS Technologies Questions

-   **Explain Handoff, and in general, how it it allows iOS and Mac/web
    apps to communicate?**

    Handoff is a feature of iOS and Mac OS X that allows a user to
    switch seamlessly between the two OSs or other devices without
    reconfiguring each device.

    To use Handoff, you create a user acitivity object for everything
    your user is doing, and update it as the user performs actions, and
    configure your app using that user activity when a user switches
    devices.

-   **What technologies/services are contained inside of iCloud?**

    iCloud is at least four difference technologies and services
    presented under a unified banner to the user. There is key-valued
    cloud storage, which is good for user preferences, settings, and
    simple app states.

    There is iCloud document storage, which is keeping you application's
    user created documents in cloud storage so they can access and
    modify them anywhere. This is related to the NSDocument and
    UIDocument class cluster.

    There is Core Data storgage, which allows a developer to take their
    applications data, whatever it might be, and sync it across devices
    using iCloud. This is related to the NSManagedObject cluster of
    classes.

    Finally, there is CloudKit storage, which allows for public and
    private cloud storage, where users can interact with one another and
    share data.

-   **What is an iOS extension? Can you list a few examples of
    popular/common extensions?**

    An app extension lets you define code which users can run from
    outside of the context of your active and running app. You might
    define an extension for use in the Today view, the Share view, edit
    a photgraph, or even make a custom keyboard on iOS.

-   **What is HealthKit?**

    HealthKit is a way for apps to register to provide health and
    fitness data for the user to view in iOS's Health app. Apps can also
    access the raw data for each source which the user has in HealthKit
    and perform it's own operations on it.

-   **What is HomeKit?**

    HomeKit provides a standardized way for connected home automation
    devices to communicate. Users can configure devices and actions and
    trigger them with Siri using HomeKit.

-   **What is Apple Pay? Could you describe a way we could use it in our
    applications?**

    Apple Pay takes the PassKit framework from iOS and allows users to
    enter in their bank accounts as passes. A way you could use this in
    your application is if you want to allow users to buy goods or
    services at your store, utilizing Apple Pay as a point of sale
    system.

-   **Explain application sandboxing.**

    Application sandboxing is limiting a program's capabilities to match
    it's expected behavior. It might not allow access to certain APIs if
    the user has not granted the program the permission to use them,
    such as local services or address book integration.

-   **What is VoiceOver? Explain some of the accessibility features
    included in iOS and how developers can utilize them.**

    VoiceOver increases accessibility for blind and low-vision users,
    and for users with certain learning challenges. If standard, library
    provided UIViews are used, almost no, if any, additional work is
    required to use accesibility features. If you go more custom, you're
    going to have to define how VoiceOver with more information to
    accurately describe your app.

-   **How does application multitasking work on iOS?**

    If a user is finished using an app for the time being, first the
    application goes into a background state. This is the first step in
    the application being suspended. In this period, the app can ask for
    more execution time or to execute certain tasks in the background.
    Barring these possibility, the app is suspended. This is when apps
    are in memory but not executing code. As other apps are brought to
    be active and if the user doesn't bring the app back to an active
    state, the app may be purged from memory to make room for other
    apps.

    The states are:

    -   Not running, not been launched or been terminated.
    -   Inactive, the app is in the foreground but not currently
        receiving events.
    -   Active, the app is running. Foreground.
    -   Bacgrkound, the app is in the background and executing code, but
        unless it requests more time, it will be only briefly.
    -   Suspended, the app was executing and is no longer, but has been
        placed in memory in antipation of becoming active again. Can be
        purged.

-   **What features does Game Center offer for iOS games?**
    -   Configure leaderboards and sets
    -   Configure achievments
    -   Configure groups
    -   Matchmaking and multiplayer

-   **What are iBeacons?**

    iBeacons are bluetooth devices that can be used to let your app know
    how close a device is to a beacon. For instance, if iBeacons were on
    a hiking trail, and iOS developer could use the Core Location
    framework to determine which trail a user was on, and then display
    information about the trail as the get close to each beacon.

-   **What is Cocoa/Cocoa Touch?**

    Cocoa include the Foundation and AppKit frameworks, and it is used
    for developing applications for Mac OS X.

    Cocoa Touch includes Foundation and the UIKit frameworks, and it is
    used for developing applications that run on iOS.

    The term “Cocoa” has been used to refer generically to any class or
    object that is based on the Objective-C runtime and inherits from
    the root class, NSObject.

    The Foundation framework implements a root class, NSObject, and
    includes internationalization, persistence, filesystem access. It's
    the level at which one uses ports, threads, locks, and processes.
    Foundation is based on the Core Foundation framework.

    AppKit and UIKit are for developing an application's user interface.

-   **Explain in general, what Core Audio, Core Data, and Core Location
    are, and how they help iOS apps.**

    -   Core Audio: Core Audio provides software interfaces for
        implementing audio features in applications you create for iOS
        and OS X. Under the hood, it handles all aspects of audio on
        each of these platforms. In iOS, Core Audio capabilities include
        recording, playback, sound effects, positioning, format
        conversion, and file stream parsing

    -   Core Data: This manages the data model of an app in terms of MVC
        design pattern. At runtime, entities are created, managed, and
        made available through the Core Data framework with no
        additional work above and beyond defining your schema.

    -   Core Location: Provides location and heading information to iOS
        apps. The framework uses GPS, cell, and WiFi radios to find the
        users latitude and longitude.

-   **Describe the role of SpriteKit and SceneKit.**

    SpriteKit is a graphic rendering and animation infrastructure that
    you can use to animate textured images. It is meant for games and
    visualizations, and does most of the work of making sure that
    drawing in a scene is as efficient as possible on iOS hardware.

    SceneKit is a framework for building simple games and app user
    interfaces with 3D graphics. SceneKit lets you define your 3D scene
    in terms of cameras, actors, bounds, light, and content, and then
    translates that into the necessary optimaized lower-level OpenGL ES
    code.

-   **What is Metal?**

    The Metal shading language is a unified programming language for
    writing both graphics and compute kernel functions that are used by
    apps written with the Metal framework.

### Questions

-   What is the responder chain? How does it work?
-   What are the different actions that buttons and other controls can
    respond to?
-   What is the role of the application delegate?
-   Explain NSUserDefaults. How would you serialize an array to disk?
-   How would you store user's credentials?
-   Explain Keychain Services.
-   Why are caching and compression important on mobile devices?
-   Explain \~/Documents, \~/Library, \~/tmp. What directory is \~ on
    iOS?
-   How does AirPlay work? How would you use it (programmatically) to
    enhance the utility and presentation of an app?
-   Give a brief overview of what sensors, IO and communication methods
    (Wifi, telephony, etc) are available on iOS. How can you make use of
    these?
-   What are the hardware performance differences among the iPad 2 /
    iPad mini 1-3, iPad Retina, iPad Air 2, iPhone 5, 5s, 6, and 6+.
    What do these constraints mean for performance intensive apps?
-   What does Cocoa Touch include and not include?
-   Why do Cocoa Touch classes start with two capital letters?
-   What is Swift, what is Objective-C and how do they relate and
    compare?
-   Explain why optionals are useful in Swift.
-   Explain `NSError` and how it works (or doesn't) in Swift.
-   How does `instancetype` work and how is it useful?
-   When is `let` appropriate in Swift? `var`?
-   Why and where is the `map` function useful.
-   How do you track down bugs? What are your tools of choice?
-   You found a bug in Cocoa. What do you do?
-   There is a regression in a new distributed version of our app
    causing crashes. How do you mitigate it? How will you prevent new
    bugs from reaching customers?
-   How are Objective-C classes implemented? Describe how the
    Objective-C runtime is implemented.
-   What security does iOS offer to protect customers and privileged
    information?
-   Our app downloads data and displays it immediately. In accordance
    with MVC where is the best place to perform the download?
-   How does MVC influence the design of a codebase?
-   What methods are part of the controller life-cycle? The view
    life-cycle?
-   What design patterns does iOS make use of? What design patterns do
    you use in your codebase?
-   What queues does iOS provide and how can you best utilize them?
-   Give a brief description of how `UIScrollView` is implemented. How
    does it operate with gesture recognizers, multiple touches and the
    run loops?
-   What API would you add or improve on iOS?
-   What is the screen resolution of the iPhone 5, 6, 6+. and iPad Air
    2?
-   What units is the resolution measured in?
-   Explain the purpose of Interface Builder, what is a NIB file?
-   What image filetype should iOS UI assets be saved in?
-   Describe some differences between a Storyboard and a standard NIB
    file.
-   What is the device status bar? How tall is it in points? Is it
    opaque or transparent? What does it do during a phone call or
    navigation?
-   What is a navigation bar? Can you show me an Apple app on your phone
    that uses a navigation bar?
-   What is a tab bar? What is a toolbar? Compare and contrast them.
-   What is a table view? What is a collection view?
-   Describe when a popover is most appropriate.
-   What is a split-view controller?
-   What sort of content would be appropriate to place in a picker view?
-   When are a label, text field and text view appropriate?
-   What does a segmented control do?
-   What is a modal view?
-   What kind of notifications does iOS offer?
-   What is an iOS app icon? Describe it as best as you can.
-   What is the smallest size an app icon could be? What's the largest
    size it could be?
-   Can an app icon contain any transparency?
-   How does a Newsstand icon differ from a regular app icon?
-   Explain a launch image.
-   Describe the purpose of Auto Layout, and in general, how it works.
-   Describe the role of animation in design of software.
-   Describe the role of interactivity and feedback when designing
    software.
-   What are some differences to take into account when building an
    iPhone app vs an iPad app?
-   Describe the importance and role of prototyping when working on an
    app design.
-   How do In-App Purchases work? What can be purchased with IAP?
-   Have you ever submitted an app to the App Store? Can you explain the
    general process?
-   What is iTunes Connect?
-   What is a provisioning profile?
-   What is an App ID?
-   What are the differences between Development and Production iOS
    signing certificates?
-   How is TestFlight used? How were UUIDs used in ad-hoc app
    distribution?
-   When do purchase receipts need to be verified?
-   What is required to display iAds?