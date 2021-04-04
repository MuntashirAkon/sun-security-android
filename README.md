# sun.security for Android

Android port of [`sun.security` API from JDK7](http://hg.openjdk.java.net/jdk7/jdk7/jdk/file/9b8c96f96a0f/src/share/classes/sun/security). Android actually have this API but only partially and is very restrictive.

[![](https://jitpack.io/v/MuntashirAkon/sun-security-android.svg)](https://jitpack.io/#MuntashirAkon/sun-security-android)

## Quick start
apksig for Android is available via JitPack.

```groovy
// Top level build file
repositories {
    maven { url "https://jitpack.io" }
}

// Add to dependencies section
dependencies {
    implementation 'com.github.MuntashirAkon:sun-security-android:1.0'
}
```

Use `android.sun.security` instead of just `sun.security` for package names. It also contains the calendar API which can be used to create certificates.

### Register KeyStores
Override `Application#onCreate()` and put the following line there:
```java
Security.addProvider(new JavaKeyStoreProvider());
```

## Features
It contains support for the following. See Java docs on `sun.security` for their usage.
  * Support for `pk8`
  * `JKS` and `PKCS12`
  * Anything under `sun.security.x509`
