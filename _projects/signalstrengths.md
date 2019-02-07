---
layout: "project"
type: "android-library"
title: "Signal Strengths"
description: "A library and sample application with the purpose of getting an accurate signal strength on different Android phones."
repo: "fennifith/SignalStrengths"
git: "git://github.com/fennifith/SignalStrengths.git"
links: 
  - name: "GitHub"
    url: "https://github.com/fennifith/SignalStrengths"
    icon: "https://github.com/favicon.ico"
  - name: "Issues"
    url: "https://github.com/fennifith/SignalStrengths/issues"
    icon: "/images/ic/bug.svg"
  - name: "Apache License 2.0"
    url: "https://choosealicense.com/licenses/apache-2.0/"
    icon: "/images/ic/copyright.svg"
  - name: "Bintray"
    url: "https://bintray.com/18jafenn90/maven/signalstrengths"
    icon: "/images/ic/launch.svg"
  - name: "app-debug.apk (v0.2 stable)"
    url: "https://github.com/fennifith/SignalStrengths/releases/download/v0.2/app-debug.apk"
    icon: "/images/ic/download.svg"
contributors: 
  - login: "fennifith"
    avatar: "https://avatars1.githubusercontent.com/u/13000407?v=4"
    url: "https://github.com/fennifith"
languages: 
  - "Java"
isDocs: "true"
isWiki: "false"
pushed: "2018-10-18T19:15:47Z"
---

SignalStrengths is a library and sample application with the purpose of getting an accurate signal strength on different Android phones.

For testing and experimentation purposes, a sample apk can be downloaded [here](https://jfenn.me/projects/signalstrengths).

## Usage

### Setup

The Gradle dependency is available through jCenter, which is used by default in Android Studio. To add the module to your project, copy this line into the dependencies section of your build.gradle file.
``` gradle
compile 'james.signalstrengths:signalstrengths:0.0.4'
```

### Listening for Signal Changes

To get your app to listen for a signal change, use [TelephonyManager.listen](https://developer.android.com/reference/android/telephony/TelephonyManager.html#listen(android.telephony.PhoneStateListener, int)) with a [PhoneStateListener](https://developer.android.com/reference/android/telephony/PhoneStateListener.html). A working example of this can be seen in the [sample application](https://github.com/TheAndroidMaster/SignalStrengths/blob/master/app/src/main/java/james/signalstrengths/MainActivity.java).

### Getting a Signal Value

To obtain a signal value from a `SignalStrength` object, simply pass it to one of the methods in the `SignalStrengths` class, which will return a number from 0-4, or -1 if an error occurs. Some examples of this are below.

#### Using a Specific Method

This allows you to specify exactly which method you want to obtain a value from.

``` java
double level = SignalStrengths.get(SignalStrengths.METHOD_LEVEL, signalStrength);
```

#### First Valid Level

This gets the first valid signal level available from any method in order of accuracy. This is the most recommended way of getting a signal value, as it is the most consistently accurate across different phones and android versions. See [Excluding Methods](https://github.com/TheAndroidMaster/SignalStrengths/blob/master/README.md#excluding-methods) and [Custom Methods](https://github.com/TheAndroidMaster/SignalStrengths/blob/master/README.md#custom-methods) for ways to change this method's behavior.

``` java
double level = SignalStrengths.getFirstValid(signalStrength);
```

#### Average Level

This gets the average of all the valid levels. To exclude a level, see [Excluding Methods](#excluding-methods).

``` java
double level = SignalStrengths.getAverage(signalStrength);
```

### Excluding Methods

The list of methods used by `SignalStrengths` can be accessed using `SignalStrengths.getMethods()`. An example of how to exclude a method is below.

``` java
SignalStrengths.getMethods().get(5).setExcluded(true);
```

### Custom Methods

It is also possible to add your own method to the list of methods used by SignalStrengths. An example for how to create a new method is below.

``` java
SignalStrengths.getMethods().add(new SignalMethod("Method Id") {
  @Override
  public double getLevel(SignalStrength signalStrength) {
    return new Random().nextDouble();
  }
});
```
