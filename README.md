# Messaging
This is the [stock SMS app from AOSP](https://android.googlesource.com/platform/packages/apps/Messaging/),
configured as an Android Studio project so that it can be built *without having to download and compile all of AOSP*.
It builds with Build Tools version 29.0 using Android Studio 4.0.0

**Please do NOT create bug reports here. Use https://issuetracker.google.com/issues?q=componentid:192810 instead.**
I'm not a Google *et al.* employee.

## How usable is this?
There's a [long list of branches and tags](https://android.googlesource.com/platform/packages/apps/Messaging/+refs) upstream
and I really don't know what they refer to, which ones are stable (if any).
I've picked a few branches based on best judgement, but things are generally unstable.
For example, although `minSdk` is set as **19** for this app, it's been unusable on pre-24 devices for some time, and
its developers do not seem to notice the backward incompatible changes they've committed until someone steps up and complains.
There's also a long standing issue of missing notifications on Oreo+ devices.
