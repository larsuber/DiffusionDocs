Diffusion
========

Social networking for iOS

Features
--------

* Share on the iOS built-in social networks
* Supports Facebook, Twitter, and more
* Easily extendable with custom UIActivities


Requirements
------------

* Unity 4.2 or higher
* iOS 6.0 or higher

***


Installation
============

Install the Unity package and drop the Diffusion prefab into your scene, then you're ready to go. 

Send a `Share()` message to the prefab to share your content! 

*** 


Configuration
=============

Platforms to hide
-----------------

The networking menu is generated automatically based on what type of data you want to share, and 
what platforms are available. If the user has not signed into Facebook, it will not show up in 
the list, for example. However, sometimes options will show up that you do not actually want. For 
example if you're only sharing text, you may get a "Copy" option which isn't very useful. 

This selection will allow you to explicitly hide options that you do not want to show. Many are 
disabled by default. 


Custom Platforms
----------------

Diffusion offers an interface for using external UIActivities. To use them, you need to include the 
files provided by the UIActivity into `Plugins/iOS` in your Unity project, and add the class to the
Custom Platforms field on the Diffusion prefab.

In order for Diffusion to access the classes for your custom UIActivity, you'll need to create a new 
category that includes the headers. You can do this through the new file menu in Xcode, or by hand. 
A template is included in the `Custom Platforms` folder. 


Messages
========

If you connect a GameObject into the Event Receiver field on the Diffusion prefab, it will these 
messages will be sent to it.

> Do **not** put your event receiver script on the prefab.


#### OnCompleted(DiffusionPlatform platform) 
Sharing completed successfully. Returns the platform the user selected to share with.

#### OnCancelled()
User cancelled the sharing process. 


Delegates
---------

For slightly better performance, or if multiple listeners are necessary, the above events are 
also exposed as delegates.

***


Notes
=====

* Twitter's URL shortener assumed any URL to be 22 characters (20, plus spaces). In reality, there
is a bug in the UIActivity's character counting, and URLs show as 36 characters. 

***


Support
=======

For support or to report any issues, please contact me at [cbaltzer@gmail.com](mailto:cbaltzer@gmail.com) or [@cbaltzer](https://twitter.com/cbaltzer) on Twitter.

