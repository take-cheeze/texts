* [how to use ant](http://developer.android.com/tools/building/building-cmdline.html)
* [app signing](http://developer.android.com/tools/publishing/app-signing.html)
* [version status](http://developer.android.com/about/dashboards/index.html)
* [Android x86](http://www.android-x86.org/)
* [AndroVM](http://androvm.org/blog/)
  * Android for virtual machines
* [connect bot](https://code.google.com/p/connectbot/)
  * ssh client for android

# Dalvik VM
* VM used in android
* register based VM
* no compatible with Java byte code
* [repository](https://github.com/android/platform_dalvik)
* [GC](http://www.adamrocker.com/blog/248/overview-of-the-dalviks-object-management.html)

# Activity
* [Tutorial](http://www.javadrive.jp/android/activity/)

# Touch Event
* [Getting single touch event](http://wiki.livedoor.jp/moonlight_aska/d/%A5%BF%A5%C3%A5%C1%A5%A4%A5%D9%A5%F3%A5%C8%A4%F2%BC%E8%C6%C0%A4%B9%A4%EB)
* [handling multi-touch event](http://wiki.livedoor.jp/moonlight_aska/d/%A5%DE%A5%EB%A5%C1%A5%BF%A5%C3%A5%C1%A5%A4%A5%D9%A5%F3%A5%C8%A4%F2%BC%E8%C6%C0%A4%B9%A4%EB)
* [about touch event](http://techbooster.jpn.org/andriod/application/715/)

# [AndroidManifest.xml](http://developer.android.com/guide/topics/manifest/manifest-intro.html)

# Screen Orientation
* [AndroidManifest.xml setting](http://masao6739.blog89.fc2.com/blog-entry-2.html)
* [orientation setting](http://wiki.livedoor.jp/moonlight_aska/d/%B2%E8%CC%CC%A4%CE%B8%FE%A4%AD%A4%F2%BC%E8%C6%C0%A4%B9%A4%EB)
* [getting screen orientation from Java](http://www.techmaru.net/wordpress/20100831/zikkiorientation/)

# NDK
* [native CUI app](http://dsas.blog.klab.org/archives/51809744.html)
* [How to build NDK executable](http://d.hatena.ne.jp/itog/20101117/1289953550)
* [SDL app builder](https://github.com/pelya/commandergenius)
  * autotools script is replaced by Android.mk
* [ubuntu ppa](http://www.upubuntu.com/2012/05/how-to-install-android-sdk-release-18.html)
* [The first NDK App](http://www.xn--rhq6sw9f0w7aevaf9ak89m.jp/android/androidLecture/firstNDKApplication/firstNDKApplication.html)
* [building and executing hello-jni](http://d.hatena.ne.jp/bs-android/20090707/1246952991)
* [About NDK-r5](http://blog.cnu.jp/2010/12/07/android-ndk-r5/)
* [creating game only with native code](http://d.hatena.ne.jp/miujun/20110111)
* [OpenSL programming](http://d.hatena.ne.jp/miujun/20120307)
* [Native Code Tutorial](http://www.altdevblogaday.com/2011/12/09/running-native-code-on-android-part-1/)
* [libev, libeio porting](http://laurentdesegur.wordpress.com/2011/10/07/building-libev-and-libeio-with-android-ndk/)
* [detecting NDK](http://annoyingtechnicaldetails.wordpress.com/2012/02/01/which-macros-does-the-android-ndk-gcc-define/)
  * use __ANDROID__ macro

## Androgenizer
* tool to create Android.mk for autotools based project
* [repository](http://cgit.collabora.com/git/user/derek/androgenizer.git)
* [article](http://blogs.igalia.com/eocanha/2012/01/30/from-source-code-to-ndk-build-using-autotools-and-androgenizer/)

## Endian
* [Detecting with header](http://stackoverflow.com/questions/6212951/endianness-of-android-ndk)
* Using header detecting is sometimes dangerous so use dynamic detection if possible.

## C++
* [What you should know before using NDK](http://usagi.hatenablog.jp/entry/2012/06/20/225404)
  * Little old.
  * Has better C++ support via libstdc++ currently.
  * Maybe get better with libc++ in clang.
* Supported c++ standard library
  * gnu libstdc++
  * stlport

## JNI
* [JNI tips](http://developer.android.com/training/articles/perf-jni.html)
* [JNI Tutorial](http://d.hatena.ne.jp/bs-android/20090324/1237864333)
* [Native API](http://mobilepearls.com/labs/native-android-api/)

## Test and Debug
* [Testing](http://vilimpoc.org/blog/2010/09/26/straightforward-android-native-executables/)
* [Debugging](http://android-developers.blogspot.jp/2011/07/debugging-android-jni-with-checkjni.html)

## [Native Activity](http://developer.android.com/reference/android/app/NativeActivity.html)
* Can be used from android-api-level-9(simply android-9 or android 2.3)
* [Native Activity Tutorial](http://www.altdevblogaday.com/2012/02/28/running-native-code-on-android-part-2/)
* [NDK Documentation](http://www.kandroid.org/ndk/docs/NATIVE-ACTIVITY.HTML)
* [How native_app_glue works](http://techbooster.jpn.org/andriod/application/2239/)
* [using native activity](http://wlog.flatlib.jp/item/1493)

## Boost
* [building](http://yutopp.hateblo.jp/entry/2011/12/26/233059)
* [fixing errors in Android](http://stackoverflow.com/questions/11444169/error-while-compiling-boost-in-android)
  * Thread and Filesystem

## ndk-build
* [usage](http://salt.air-nifty.com/salt/2010/05/android-ndk-r4.html)
* [logging](http://otake.knowd2.com/drupal-rotake/?q=node/103)
* [options](http://mandroid.blog106.fc2.com/blog-entry-27.html)
* [reference](http://blog.makotokw.com/memo/android/android-ndk/)

## Full native android app
* From NDK r5 full native app(that means no Java code) is possible.
* [article about it](http://android-developers.blogspot.jp/2011/01/gingerbread-ndk-awesomeness.html)
  * Has example event loop code.
* Eclipse is not required now.

## autotools
* [script for it](http://forum.xda-developers.com/showthread.php?t=1667102)

## Application.mk
* [document](http://www.kandroid.org/ndk/docs/APPLICATION-MK.html)

## Android.mk
* Makefile script but has many special variables.
* [document](http://www.kandroid.org/ndk/docs/ANDROID-MK.html)
* Androgenizer
  * [Repository](http://cgit.collabora.com/git/android/androgenizer.git/)
  * [Readme](http://cgit.collabora.com/git/android/androgenizer.git/tree/README.txt)
  * [androgenizer description](http://derekforeman.blogspot.jp/2012/04/androgenizer-porting-libtoolized.html)
  * [usage](http://blogs.igalia.com/eocanha/2012/01/30/from-source-code-to-ndk-build-using-autotools-and-androgenizer/)