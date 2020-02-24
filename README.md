# Messaging
This is the [stock SMS app from AOSP](https://android.googlesource.com/platform/packages/apps/Messaging/), configured as an Android Studio project so that it can be built *without having to download and compile all of AOSP*. It builds with Gradle Plugin version 3.5.3 and Build Tools version 28.0 using Android Studio 3.5.3

The **goal** is not to fix and/or enhance this Google _et al._ owned app outside its premises, but rather _study, observe, experiment with_ and other reasons you can think of. Source code changes, if any, are kept at a minimum.

## Structure
There are 3 branches:  
**9.0** follows a recent *android-9.0.0_rXX* tag from upstream (check `ext.verName` in top level build.gradle).  
Likewise, **10.0** follows a recent *android-10.0.0_rXX* tag from upstream.  
**goplay** is a fork of **9.0** branch with modifications required by Google Play (yes, Google finds its original app unacceptable to Play market).

## How usable is this?
**9.0** and **10.0** branches are the closest to original app. They should be as stable as Google _et. al_ intended them to be.  
In order to be accepted to Play market, **goplay** branch bumps `targetSdkVersion` to 28 which causes notifications to disappear on Android 8+ devices and intermittent crashes, because of the backward-incompatible changes "Android Team" has progressively been introducing to the SDK.  
Currently *android-10.0.0_rXX* tagged snapshots at upstream exhibit a "seemingly premature" `targetSdkVersion=28` setting in their AndroidManifest.xml, as modifications required to handle notifications for that level were not observed in their sources.

## Help Wanted
There's a [long list of branches and tags](https://android.googlesource.com/platform/packages/apps/Messaging/+refs) upstream and I really don't know what they refer to, which ones are stable (if any), etc.
My selection of tags are merely based on intuition/guesswork. If you have any insight beyond what I've summoned, how different the SDKs we use are from that of AOSP, etc. then please create an Issue and enlighten us. Thank you.
