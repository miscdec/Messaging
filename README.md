# Messaging
This is the [stock SMS app from AOSP](https://android.googlesource.com/platform/packages/apps/Messaging/), configured as an Android Studio project so that it can be built *without having to download and compile all of AOSP*. It builds with Gradle Plugin version 3.5.3 and Build Tools version 28.0 using Android Studio 3.5.3

The **goal** is not to fix and/or enhance this Google _et al._ owned app outside its premises, but rather _study, observe, experiment with_ and other reasons you can think of. Source code changes, if any, are kept at a minimum.

## Structure
There are 2 branches:  
**9.0** follows a recent *android-9.0.0_rXX* tag from upstream (check `ext.verName` in top level build.gradle).  
**goplay** is a fork of that branch with modifications required by Google Play (yes, Google finds its original app unacceptable to Play market).

## How usable is this?
**9.0** branch is the closest to original app. It should be as stable as Google _et. al_ intended it to be.  
In order to be accepted to Play market, **goplay** branch bumps `targetSdkVersion` to 28 which causes notifications to disappear on Android 8+ devices and intermittent crashes, because of the backward-incompatible changes "Android Team" has progressively been introducing to the SDK.
