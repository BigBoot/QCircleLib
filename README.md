#QCircleLib [![Release](https://img.shields.io/github/tag/BigBoot/QCircleLib.svg?label=QCircleLib)](https://jitpack.io/#BigBoot/QCircleLib/)


QCircleLib allows you to create applications for QuickView, a 3rd party implementation of LG's QuickCircle 
for the LG G3 QuickCircle case.
For more information about QuickView visit the 
[XDA-Thread](http://forum.xda-developers.com/showpost.php?p=59892931&postcount=128).

##Include this library in your Project
###Step 1. Add the JitPack repository to your build file
```groovy
repositories {
    maven {
        url "https://jitpack.io"
    }
}
```
###Step 2. Add the dependency
```groovy
dependencies {
        compile 'com.github.BigBoot:QCircleLib:v1.0.2'
	}
```

##Using the library
###Step 1. Create a new Activity extending QCircleView
```java
public class YourActivity extends QCircleActivity{
    @Override
    protected CircleView onCreateView(CircleViewBuilder builder) {
        return builder.build(R.layout.your_layout);
    }
}
```

###Step 2. Add a intent-filter to your activity
```xml
<activity
    android:name=".YourActivity"
    android:label="@string/app_name"
    android:icon="@drawable/app_icon" >
    <intent-filter>
        <action android:name="de.bigboot.qcircleview.qcircleapp" />
    </intent-filter>
</activity>
```
Your application should appear on QuickView.
This will automatically fit your view inside the visible circle and add a back button to it.
If you need more control over this look at [Customizing the view](#customizing-the-view)

##Customizing the view
To customize your view, you just need to set the corresponding options before calling Builder.build().
For example to disable the back button:
```java
@Override
protected CircleView onCreateView(CircleViewBuilder builder) {
    builder.setShowReturnButton(false);
    return builder.build(R.layout.your_layout);
}
```

To completely disable any screen restrictions and use the full screen:
```java
@Override
protected CircleView onCreateView(CircleViewBuilder builder) {
    builder.setUseMask(false);
    return builder.build(R.layout.your_layout);
}
```

#Javadoc
The javadoc is available [here](https://jitpack.io/com/github/BigBoot/QCircleLib/v1.0.2/javadoc/)

#License
```
Copyright 2015 Marco Kirchner

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
