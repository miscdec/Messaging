# Messaging
This is the [stock SMS app from AOSP](https://android.googlesource.com/platform/packages/apps/Messaging/), configured as an Android Studio project so that it can be built *without having to download and compile all of AOSP*. It builds with Gradle Plugin version 3.5.3 and Build Tools version 28.0 using Android Studio 3.5.3

The **goal** is not to fix and/or enhance this Google _et al._ owned app outside its premises, but rather _study, observe, experiment with_ and other reasons you can think of. Source code changes, if any, are kept at a minimum.

## Structure
There's a [long list of branches and tags](https://android.googlesource.com/platform/packages/apps/Messaging/+refs) upstream and I really don't know what they refer to, which ones are stable (if any). So far I've been _experimenting with_ several tags/branches, none of which proved to be stable. "App Vitals" page of this app in my Play developer account is flooded with reports of ANRs and crashes, no matter which tag/branch I follow. Caveat emptor!

Having said that, currently there are 4 branches in this repo:  
**9.0** follows a recent *android-9.0.0_rXX* tag from upstream (check `ext.verName` in top level build.gradle).  
Likewise, **10.0** follows a recent *android-10.0.0_rXX* tag from upstream.  
**sdk-release** is a sync of the same branch upstream.  
**goplay** is a fork of **sdk-release** with modifications required by Google Play (yes, Google finds its original app unacceptable to Play market).

## How usable is this?
I reckon **9.0** branch is the closest to original app. It should be as stable as Google _et. al_ intended it to be. There is an APK of this branch under releases section (however, it is not possible to submit this revision to Play market).  
**sdk-release** has the most recent commits and is currently ahead of both **9.0** and **10.0**.  
In order to be accepted to Play market, **goplay** branch bumps `targetSdkVersion` to 28 which causes notifications to disappear on Android 8+ and intermittent crashes, because of the backward-incompatible changes "Android Team" has progressively been introducing to the SDK.

Currently *android-10.0.0_rXX* tagged revisions at upstream exhibit a "seemingly premature" `targetSdkVersion=28` setting in their AndroidManifest.xml, as modifications required to handle notifications for that level were not _observed_ in their sources. This is reflected at **10.0** here.
