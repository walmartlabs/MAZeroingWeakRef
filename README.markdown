***
# NOTICE:

## This repository has been archived and is not supported.

[![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/)
***
NOTICE: SUPPORT FOR THIS PROJECT HAS ENDED 

This projected was owned and maintained by Walmart. This project has reached its end of life and Walmart no longer supports this project.

We will no longer be monitoring the issues for this project or reviewing pull requests. You are free to continue using this project under the license terms or forks of this project at your own risk. This project is no longer subject to Walmart's bug bounty program or other security monitoring.


## Actions you can take

We recommend you take the following action:

  * Review any configuration files used for build automation and make appropriate updates to remove or replace this project
  * Notify other members of your team and/or organization of this change
  * Notify your security team to help you evaluate alternative options

## Forking and transition of ownership

For [security reasons](https://www.theregister.co.uk/2018/11/26/npm_repo_bitcoin_stealer/), Walmart does not transfer the ownership of our primary repos on Github or other platforms to other individuals/organizations. Further, we do not transfer ownership of packages for public package management systems.

If you would like to fork this package and continue development, you should choose a new name for the project and create your own packages, build automation, etc.

Please review the licensing terms of this project, which continue to be in effect even after decommission.

MAZeroingWeakRef - by Mike Ash - mike@mikeash.com

Introduction
------------

MAZeroingWeakRef is a library for using zeroing weak references in retain/release Cocoa and Cocoa Touch code. These are references which do not keep an object alive, and which automatically become nil once the object is destroyed.

MAZeroingWeakRef does not work under Cocoa garbage collection. The built-in __weak specifier exists for that, although it is used somewhat differently.

The API is simple and mostly self-explanatory from the header file. Note that cleanup blocks are only needed for advanced uses when you need to take more action than simply zeroing the reference when the target object is destroyed. Be sure to heed the warning in the header about not doing too much work in the cleanup block.

In order to allow weak references to CoreFoundation bridged objects, a fair amount of crazy hacking of private APIs had to be done. For people who don't like that sort of thing, or who are worried about rejection when building for iOS, this crazy hacking can be reduced or disabled altogether. Look at the COREFOUNDATION_HACK_LEVEL macro in MAZeroingWeakRef.m, and the comment above it which explains what the different levels do.

A similar KVO_HACK_LEVEL macro is also available.

App Store
---------

For iOS work, or Mac App Store work, you will probably want to set both COREFOUNDATION_HACK_LEVEL and KVO_HACK_LEVEL to `0`. In this mode, MAZeroingWeakRef uses no private APIs.

Also, if you need your app to run on iOS 3.x you need to disable blocks based code setting USE_BLOCKS_BASED_LOCKING to `0`.

Source Code
-----------

The MAZeroingWeakRef code is available from GitHub:

    http://github.com/mikeash/MAZeroingWeakRef

MAZeroingWeakRef is made available under a BSD license.

More Information
----------------

For more information about it, this blog post gives a basic introduction to the API:

    http://mikeash.com/pyblog/introducing-mazeroingweakref.html

This describes how it works in most cases:

http://mikeash.com/pyblog/friday-qa-2010-07-16-zeroing-weak-references-in-objective-c.html

And this describes some of the more hairy parts:

    http://mikeash.com/pyblog/friday-qa-2010-07-30-zeroing-weak-references-to-corefoundation-objects.html

Enjoy!
