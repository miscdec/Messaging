# Messaging
This is the [stock SMS app from AOSP](https://android.googlesource.com/platform/packages/apps/Messaging/),
configured as an Android Studio project so that it can be built *without having to download and compile all of AOSP*.
It builds with Build Tools version 29.0 using Android Studio 4.0.0

**Please do NOT create bug reports here. Use https://issuetracker.google.com/issues?q=componentid:192810 instead.**
I'm not a Google *et al.* employee.

----
### Because of the issue stated in the Note below, this app has been REMOVED FROM PLAY STORE until further notice. Only use the latest APK released here.
----

> **NOTE :**  
> This app requires `targetSdk` set to 24. Any higher Sdk level causes notifications to disappear on Oreo and later devices.
> However, Google Play does not accept apps with `targetSdk` set to lower than 28. Therefore, the version you install from Play
> will experience missing notifications if you have Oreo and later device. In that case, **do not install this app from Google Play,
> get the latest APK released here.** It is built with `targetSdk=24`.
----

## How usable is this?
There's a [long list of branches and tags](https://android.googlesource.com/platform/packages/apps/Messaging/+refs) upstream
and I really don't know what they refer to, which ones are stable (if any).
I've picked a few branches based on best judgement, but things are generally unstable.

For example, although `minSdk` is set to **19** for this app, it's been unusable on all but latest API level for some time, and
its developers do not seem to notice the backward incompatible changes they've committed until someone steps up and complains.  
The code base looks abandoned, and whatever commits have been made seem to serve some engineer's narrow interest
to test something new in the AOSP stack.  
Fixes, if any, are mostly band-aid like workarounds.  
API level differences are buried in a soup of if-then-else code paths, instead of properly extending and
making use of Java's polymorphic features. There's, however, a ridiculously over-engineered data layer considering the fact
that this app only displays items in a Listview with no means to categorize, query, sort, etc.  

Overall it's been quite an unpleasant experience and distasteful glimpse into a part of AOSP for me, that reaffirmed
my doubts on the quality of open source code as shared with the public.

## How to work on this?
Just clone the repo. Android Studio's Open Project dialog should recognize that folder as a valid Android project. Select it,
and click Open. The rest should be handled by Android Studio.

## How different is this from the original one in AOSP?
It should be identical. I deliberately tried to keep it that way. However, this app uses ProGuard as a conditional compilation tool.
So, its use is not optional. And if you skip it, the resultant app crashes. But I found a boolean flag that I can set so that the app
won't crash without ProGuard. See `util/Assert.java` for details. That is probably the most significant difference.
