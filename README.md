
# BaseNumberConverter Library
Powerful math base numbers operations library for Android developers.
This library can convert a number between two custom bases (between 2 and 62).
It works with String, so theoretically, the number limit is infinite :).
The library supports large/huge numbers in each math base. 

Common bases: base 2, base 8, base 10, base 16.
Examples:
```
    3424(10) = 110101100000(2)
    12623(10) = 314f(16)
    3a4f(16) = 11101001001111(2)
```

[![Google Play Store](https://lh4.ggpht.com/OLGti5eKo7FEYFa_dDlPC7h08FBUpc3j5xC64WIToSrOEto4L12TmRtjK4bvIjLhYQ=w200-rw)](https://play.google.com/store/apps/details?id=com.mdc.baseconverter)

<!--
# [![Build Status](https://travis-ci.org/bmarrdev/android-DecoView-charting.svg?branch=master)](https://travis-ci.org/bmarrdev/android-DecoView-charting) [![Release](https://img.shields.io/github/release/bmarrdev/android-DecoView-charting.svg?label=JitPack)](https://jitpack.io/#bmarrdev/android-DecoView-charting) [![Hex.pm](https://img.shields.io/hexpm/l/plug.svg)](http://www.apache.org/licenses/LICENSE-2.0) [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-DecoView-green.svg?style=flat)](https://android-arsenal.com/details/1/2329)
-->

Sample app available from the play store.

[![Google Play Store](https://play.google.com/intl/en_us/badges/images/badge_new.png)](https://play.google.com/store/apps/details?id=com.mdc.baseconverter)

Including BaseNumberConverter in your project
===

Download via **Maven**:
```xml
<dependency>
    <groupId>ro.mdc_software</groupId>
    <artifactId>basenumber</artifactId>
    <version>0.3</version>
</dependency>
```
Download via **Gradle**:

Step 1. Add the repositories into your build.gradle
```groovy
repositories {
    jcenter()
    
    maven {
        url  "http://dl.bintray.com/cosminmihu/android" 
    }
}
```
Step 2. Add the dependency in the form
```groovy
dependencies {
    compile 'ro.mdc_software:basenumber:0.3'
}
```
Download via **Ivy**:
```xml
<dependency org='ro.mdc_software' name='basenumber' rev='0.3'>
  <artifact name='basenumber' ext='pom' />
</dependency>
```

Download via **Bintray**:
[![Download](https://api.bintray.com/packages/cosminmihu/android/BaseNumberConverterLibrary/images/download.svg?version=0.3) ](https://bintray.com/cosminmihu/android/BaseNumberConverterLibrary/0.3/link)

Number Systems and Bases
==

Already defined **BaseNumbers**:
```groovy
    BaseNumber.ZERO;
    BaseNumber.ONE;
```

**Base Systems**
```groovy
    Base  2 - digits: 01
    Base  3 - digits: 012
    Base  4 - digits: 0123
    Base  8 - digits: 01234567
    Base 10 - digits: 0123456789
    Base 16 - digits: 0123456789ABCDEF
    ....
    Base 32 - digits: 0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ
    Base 62 - digits: 0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz
```

Usage
===

Create new BaseNumber: **ADD**
```java
    BaseNumber nbr_0_10 = BaseNumber.ZERO;
    BaseNumber nbr_0_10 = new BaseNumber();
    BaseNumber nbr_0_10 = new BaseNumber(0);
    BaseNumber nbr_0_10 = new BaseNumber("0");
    BaseNumber nbr_0_10 = new BaseNumber(0, 10);
    BaseNumber nbr_0_10 = new BaseNumber("0", 10);
    
    BaseNumber nbr_1_10 = BaseNumber.ONE;
    BaseNumber nbr_1_10 = new BaseNumber(1);
    BaseNumber nbr_1_10 = new BaseNumber("1");
    BaseNumber nbr_1_10 = new BaseNumber(1, 10);
    BaseNumber nbr_1_10 = new BaseNumber("1", 10);
    
    BaseNumber nbr_EF1_16 = new BaseNumber("EF1", 16);
```

Operation: **ADD**
```java
    BaseNumber nbr_234_10 = new BaseNumber(234, 10);
    BaseNumber nbr_23_10 = new BaseNumber(23, 10);
    BaseNumber total = nbr_234_10.add(nbr_23_10));

    Log.d("TOTAL", total.toString()); // 257(10)

    BaseNumber nbr_A102F_16 = new BaseNumber("A102F", 16);
    BaseNumber nbr_23_16 = new BaseNumber(23, 16);
    BaseNumber total = nbr_A102F_16.add(nbr_23_16));

    Log.d("TOTAL", total.toString()); // A1052(16)
```

Operation: **SUB**
```java
    BaseNumber nbr_234_10 = new BaseNumber(234, 10);
    BaseNumber nbr_23_10 = new BaseNumber(23, 10);
    BaseNumber total = nbr_234_10.sub(nbr_23_10));

    Log.d("TOTAL", total.toString()); // 211(10)

    BaseNumber nbr_A102F_16 = new BaseNumber("A102F", 16);
    BaseNumber nbr_23_16 = new BaseNumber(23, 16);
    BaseNumber total = nbr_A102F_16.sub(nbr_23_16));

    Log.d("TOTAL", total.toString()); // A100C(16)
```

Operation: **MUL**
```java
    BaseNumber nbr_234_10 = new BaseNumber(234, 10);
    BaseNumber nbr_23_10 = new BaseNumber(23, 10);
    BaseNumber total = nbr_234_10.mul(nbr_23_10));

    Log.d("TOTAL", total.toString()); // 5382(10)

    BaseNumber nbr_EA_16 = new BaseNumber("EA", 16);
    BaseNumber nbr_17_16 = new BaseNumber(17, 16);
    BaseNumber total = nbr_EA_16.mul(nbr_17_16));

    Log.d("TOTAL", total.toString()); // 1506(16)
```

Operation: **DIV**
```java
    BaseNumber nbr_5382_10 = new BaseNumber(5382, 10);
    BaseNumber nbr_23_10 = new BaseNumber(23, 10);
    BaseNumber total = nbr_5382_10.div(nbr_23_10));

    Log.d("TOTAL", total.toString()); // 234(10)

    BaseNumber nbr_1506_16 = new BaseNumber(1506, 16);
    BaseNumber nbr_17_16 = new BaseNumber(17, 16);
    BaseNumber total = nbr_1506_16.div(nbr_17_16));

    Log.d("TOTAL", total.toString()); // EA(16)
```

Operation: **MODULO**
```java
    BaseNumber nbr_5382_10 = new BaseNumber(53822, 10);
    BaseNumber nbr_23_10 = new BaseNumber(23, 10);
    BaseNumber total = nbr_5382_10.modulo(nbr_23_10));

    Log.d("TOTAL", total.toString()); // 2(10)

    BaseNumber nbr_EA4F_16 = new BaseNumber("EA4F", 16);
    BaseNumber nbr_17_16 = new BaseNumber(17, 16);
    BaseNumber total =  nbr_EA4F_16.modulo(nbr_17_16));

    Log.d("TOTAL", total.toString()); // 16(16)
```

Operation: **TBD**

<!--- just
DecoView is subclassed from the Android View class. Just like other View subclasses, such as TextView and ImageView, it can be added and configured from your layout XML then controlled in your Activity code.

This repository includes a number of samples for constructing and animating a DecoView. You will find the code for the samples in the [sampleapp project](https://github.com/bmarrdev/android-DecoView-charting/tree/master/sampleapp/src/main/java/com/hookedonplay/decoviewsample).

The main concepts you need to understand are:
- DecoView is a View, it subclasses android.view.View
- Use [SeriesItem.Builder](https://github.com/bmarrdev/android-DecoView-charting/blob/master/decoviewlib/src/main/java/com/hookedonplay/decoviewlib/charts/SeriesItem.java) to build one or more data series or your DecoView will not be visible
- Use [DecoEvent.Builder](https://github.com/bmarrdev/android-DecoView-charting/blob/master/decoviewlib/src/main/java/com/hookedonplay/decoviewlib/events/DecoEvent.java) to schedule animating events for each data series


**Add DecoView to your xml layout**

```xml
<com.hookedonplay.decoviewlib.DecoView
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/dynamicArcView"/>
```

**Configure DecoView data series in your Java code**

```java
DecoView arcView = (DecoView)findViewById(R.id.dynamicArcView);

// Create background track
arcView.addSeries(new SeriesItem.Builder(Color.argb(255, 218, 218, 218))
        .setRange(0, 100, 100)
        .setInitialVisibility(false)
        .setLineWidth(32f)
        .build());

//Create data series track
SeriesItem seriesItem1 = new SeriesItem.Builder(Color.argb(255, 64, 196, 0))
        .setRange(0, 100, 0)
        .setLineWidth(32f)
        .build();

int series1Index = arcView.addSeries(seriesItem1);

```

**Add events to animate the data series**

```java
arcView.addEvent(new DecoEvent.Builder(DecoEvent.EventType.EVENT_SHOW, true)
        .setDelay(1000)
        .setDuration(2000)
        .build());

arcView.addEvent(new DecoEvent.Builder(25).setIndex(series1Index).setDelay(4000).build());
arcView.addEvent(new DecoEvent.Builder(100).setIndex(series1Index).setDelay(8000).build());
arcView.addEvent(new DecoEvent.Builder(10).setIndex(series1Index).setDelay(12000).build());

```
 --->

Requirements
===

Android 2.3+ (API Level 9)

Credits
===

[![MDC ](http://cosminmihu.info/blog/wp-content/uploads/company_logo.png)](http://www.mdc-software.ro)


License
===

    Copyright 2016 Dumitru-Cosmin Mihu

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.