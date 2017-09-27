# Week 2

All the assignments may be created in a single project called `HelloAndroidWorld`. Create a git repository on GitLab and push the project to it.

## Assignment - Activity Lifecycle

Override at least three lifecycle callbacks. Place a log message inside of each callback.

Some examples are:
```java
Log.v("TAG", "My message");   // Verbose
Log.w("TAG", "My message");   // Warning
Log.e("TAG", "My message");   // Error
Log.d("TAG", "My message");   // Debug
```

You can now create a filter inside Android Studio for the tags.

Try messing around with the app and check when each callback method is called.

## Assignment - About

Add an about activity to your hello world application with some information about who created it.

Next place an about button on your main activity and create an intent to open the about activity when the user clicks the about button.

## Assignment - Open VIVES website

Add a `TextView` to your about activity stating something like: "This app was made by VIVES bachelor students". Change the color of this text and add a `onClick` event handler to it. Make sure that when the user touches the text, a web browser is launched and the VIVES website is shown.

## Assignment - Browser Activity

Create a new activity and add a WebView to it. Add to code to the `onCreate()` callback to handle the URL passed in the intent. Next add an intent filter to the activity so it can function as a browser.

Try it out. Does it come up as an option when you click the link in your about activity?

## Assignment - Touch location

Add two TextViews to your main activity that display the last touch location of the user inside your activity.

Make use of the correct touch event.
