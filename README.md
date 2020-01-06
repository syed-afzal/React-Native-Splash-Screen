# React-Native starter app with splash screen

## Overview

It is the simple react-native-cli project from facebook. I just added splash screen for getting  react-native starter acts more reactively.
Because it takes time to find out how to put splash screen in react-native. We used latest react version at that time, so we used one of it's
__hook__ as well.

## Prerequisite
You need node >= 8 and npm > 5.2
## GuideLine Steps

#### 1. Clone the repo

#### 2. Install package react-native-splash-screen

#### 3. Edit MainActivity.java file

Add Import statements on top

```bash
import org.devio.rn.splashscreen.SplashScreen;
import android.os.Bundle;
```

Then add this method

```
@Override
protected void onCreate(Bundle savedInstanceState){
  SplashScreen.show(this);
  super.onCreate(savedInstanceState);
}
```

#### 4. Create a layout directory
Go iniside this directory and create a folder with name __layout__

___android/app/src/main/res___

After creating a layout folder, create a file inside this folder with the name
`launch_screen.xml `

Now paste this code inside this newly created file

```bash
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
                android:orientation="vertical" android:layout_width="match_parent"
                android:layout_height="match_parent">
    <ImageView android:layout_width="match_parent"
               android:layout_height="match_parent"
               android:src="@mipmap/splash"
               android:scaleType="centerCrop" />
</RelativeLayout>

```
#### 5. Paste your images
 Go inside this directory

__android/app/src/main/res__

you see the folder with prefix mipmap-***

It is a directory where you put your images for splash screen.

Image sizes are as follows:
- mi**-hdpi => 480 X 800px
- mi**-mdpi => 320 X 480px
- mi**-xhdpi => 720 X 1280px
- mi**-xxhdpi => 960 X 1600px
- mi**-xxxhdpi => 1440 x 2560px

Put all images with these resolutions into their respective folder.

We are very near to __The End__ :smiley:

So far, all these steps are for showing splash screen, but we did't do 
anything to hide the splash screen so our last step is to hide this splash screen
and allow user to go interact with app.

#### 5. Hide the Splash 

Go inside your entry file according to your own design architecture. My 
entry file is __App.js__

Add imports

`import React, { useEffect } from 'react';`

`import SplashScreen from 'react-native-splash-screen';`

    useEffect(() => {
        SplashScreen.hide();
    }, []);
    
That's all Folks :tada:

#### Conclusion

We create a Splash Screen on latest version of react-native for `Android`. If you want to create same splash for `ios`
 you are free to contact me