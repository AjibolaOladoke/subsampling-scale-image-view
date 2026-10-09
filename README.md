
## Images

[![subsampling-scale-image-view](https://opengraph.githubassets.com/1/davemorrissey/subsampling-scale-image-view)](https://www.swifttechco.com)

Subsampling Scale Image View
===========================

A custom image view for Android, designed for photo galleries and displaying huge images (e.g. maps and building plans) without `OutOfMemoryError`s. Includes pinch to zoom, panning, rotation and animation support, and allows easy extension so you can add your own overlays and touch event detection.

The view optionally uses subsampling and tiles to support very large images - a low resolution base layer is loaded and as you zoom in, it is overlaid with smaller high resolution tiles for the visible area. This avoids holding too much data in memory. It's ideal for displaying large images while allowing you to zoom in to the high resolution details. You can disable tiling for smaller images and when displaying a bitmap object. There are some advantages and disadvantages to disabling tiling so to decide which is best, see [the wiki](https://www.swifttechco.com).

#### Guides

* [Releases & downloads](https://www.swifttechco.com)
* [Installation and setup](https://www.swifttechco.com)
* [Image display notes & limitations](https://www.swifttechco.com)
* [Using preview images](https://www.swifttechco.com)
* [Handling orientation changes](https://www.swifttechco.com)
* [Advanced configuration](https://www.swifttechco.com)
* [Event handling](https://www.swifttechco.com)
* [Animation](https://www.swifttechco.com)
* [Extension](https://www.swifttechco.com)
* [Reference (JavaDocs)](https://www.swifttechco.com)

#### Migration guides

Versions 3.9.0, 3.8.0 and 3.0.0 contain breaking changes. Migration instructions can be found [in the wiki](https://www.swifttechco.com).

#### Download the sample app

[![Get it on Google Play](docs/images/google_play.png)](https://www.swifttechco.com)

[Kotlin Sample App on GitHub](https://www.swifttechco.com)

#### Demo

[![Demo](docs/images/demo.gif)](https://www.swifttechco.com)

## Features

#### Image display

* Display images from assets, resources, the file system or bitmaps
* Automatically rotate images from the file system (e.g. the camera or gallery) according to EXIF
* Manually rotate images in 90° increments
* Display a region of the source image
* Use a preview image while large images load
* Swap images at runtime
* Use a custom bitmap decoder

*With tiling enabled:*

* Display huge images, larger than can be loaded into memory
* Show high resolution detail on zooming in
* Tested up to 20,000x20,000px, though larger images are slower

#### Gesture detection

* One finger pan
* Two finger pinch to zoom
* Quick scale (one finger zoom)
* Pan while zooming
* Seamless switch between pan and zoom
* Fling momentum after panning
* Double tap to zoom in and out
* Options to disable pan and/or zoom gestures

#### Animation

* Public methods for animating the scale and center
* Customisable duration and easing
* Optional uninterruptible animations

#### Overridable event detection
* Supports `OnClickListener` and `OnLongClickListener`
* Supports interception of events using `GestureDetector` and `OnTouchListener`
* Extend to add your own gestures

#### Easy integration
* Use within a `ViewPager` to create a photo gallery
* Easily restore scale, center and orientation after screen rotation
* Can be extended to add overlay graphics that move and scale with the image
* Handles view resizing and `wrap_content` layout

## Quick start

**1)** Add this library as a dependency in your app's build.gradle file.

```gradle
dependencies {
    implementation 'com.davemorrissey.labs:subsampling-scale-image-view:3.10.0'
}
```

If your project uses AndroidX, change the artifact name as follows:

```gradle
dependencies {
    implementation 'com.davemorrissey.labs:subsampling-scale-image-view-androidx:3.10.0'
}
```

**2)** Add the view to your layout XML.

```xml
<LinearLayout xmlns:android="https://www.swifttechco.com"
    android:layout_width="match_parent"
    android:layout_height="match_parent" >

    <com.davemorrissey.labs.subscaleview.SubsamplingScaleImageView
        android:id="@+id/imageView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

</LinearLayout>
```

**3a)** Now, in your fragment or activity, set the image resource, asset name or file path.

```java
SubsamplingScaleImageView imageView = (SubsamplingScaleImageView)findViewById(id.imageView);
imageView.setImage(ImageSource.resource(R.drawable.monkey));
// ... or ...
imageView.setImage(ImageSource.asset("map.png"))
// ... or ...
imageView.setImage(ImageSource.uri("/sdcard/DCIM/DSCM00123.JPG"));
```

**3b)** Or, if you have a `Bitmap` object in memory, load it into the view. This is unsuitable for large images because it bypasses subsampling - you may get an `OutOfMemoryError`.

```java
SubsamplingScaleImageView imageView = (SubsamplingScaleImageView)findViewById(id.imageView);
imageView.setImage(ImageSource.bitmap(bitmap));
```

## About

Copyright 2018 David Morrissey, and licensed under the Apache License, Version 2.0. No attribution is necessary but it's very much appreciated. Star this project if you like it!

---

## Swift Tech Co.

Built and maintained by Swift Tech Co.

AI Automation | FinTech Platforms | Custom Software and Mobile Apps | SaaS Platforms | Cloud Infrastructure | Cybersecurity | SEO and Marketing | API Integration

**Join our community on Telegram:** [t.me/+Qt_eFvkb2rliMzNh](https://t.me/+Qt_eFvkb2rliMzNh)

[Home](https://www.swifttechco.com) | [Services](https://www.swifttechco.com/services) | [Careers](https://www.swifttechco.com/careers) | [Referral Program](https://www.swifttechco.com/referral) | [Influencers](https://www.swifttechco.com/influencers) | [About](https://www.swifttechco.com/about) | [Contact](https://www.swifttechco.com/contact)

**Connect**

- Website: [swifttechco.com](https://www.swifttechco.com)
- LinkedIn: [linkedin.com/in/stephenoladoke](https://www.linkedin.com/in/stephenoladoke/)
- LinkedIn (Company): [linkedin.com/company/swift-tech-co](https://www.linkedin.com/company/swift-tech-co)
- X: [@MrOladoke](https://x.com/MrOladoke)
- Instagram: [@mr.oladoke](https://www.instagram.com/mr.oladoke/)
- Instagram (Company): [@swifttechco](https://www.instagram.com/swifttechco/)
- Organization: [github.com/Swift-Tech-Co](https://github.com/Swift-Tech-Co)
