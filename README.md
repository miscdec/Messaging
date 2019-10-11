# Messaging
This is the [stock SMS app from AOSP](https://android.googlesource.com/platform/packages/apps/Messaging/), configured as an Android Studio project. It builds with Gradle Plugin version 3.4.2 and Build Tools version 29.0 using Android Studio 3.4.2

~~This repo does not follow the upstream master branch, only certain tags.~~ This repo now follows master branch to get latest bug fixes.

**edit: Oct 2019**  
_When I first started this project, I was hoping to build it with no changes to Java sources, just reorganize things per Android Studio._
_It turned out this app has some issues, lot of dead code and needs serious refactoring. I've also observed there are fixes to some bugs on private repos owned by some device vendor's engineers, only to be pushed to master branch years later, if you're lucky._  
_I don't know how many other embedded apps in AOSP are like this. But I'm inclined to think that AOSP does not work out of the box, and should not be relied on as shared with the public._

_Anyway.. as you can see, this is a big project for Android Studio, and my notebook with dual-core CPU, 8GB RAM and some old GPU which Android Emulator does not support for OpenGL acceleration does not cut it. At least a quad-core CPU, 16GB RAM, modern GPU supported by the emulator, SSD and a second monitor is needed to carry out even simple tasks. There's a Sponsor button at the top in case you're interested. Until then..._
