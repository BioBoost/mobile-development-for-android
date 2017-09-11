<!-- toc -->

# Hello Android World

For the development of Android applications we will make use of an IDE (Integrated Development Environment) called Android Studio. This is the official standard and is considered the best (only) option out there.

## Android Studio

Android Studio is the official IDE for Google's Android operating system, built based on JetBrains' IntelliJ IDEA software and designed specifically for Android development. It is available for download on Windows, macOS and Linux based operating systems. It is a replacement for the Eclipse Android Development Tools (ADT) as primary IDE for native Android application development.

The current stable version is 2.3.3, released in June 2017. Next major update, version 3.0, is in preview stage as of August 2017.

Since we love working on the edge, we will be using the preview version, eagerly awaiting the stable release of it. Navigate to (https://sillevl.gitbooks.io/software-installation-guide)[https://sillevl.gitbooks.io/software-installation-guide] and follow the installation guide to install the latest Android Studio 3.0 version.

### Some cool features

Android Studio has some cool and fancy features, some of which are:

* **Fast and feature-rich emulator:** Install and run your apps faster than with a physical device and test your app on virtually any Android device configuration: Android phones, Android tablets, Android Wear, and Android TV devices. The new Android Emulator 2.0 is faster than ever and allows you to dynamically resize the emulator and access a suite of sensor controls.

* **Intelligent code editor:** Write better code, work faster, and be more productive with an intelligent code editor that helps you each step of the way. Android Studio is built on IntelliJ and is capable of advanced code completion, refactoring, and code analysis.

* **Instant Run:** Push code and resource changes to your app running on a device or emulator and see the changes instantly come to life. Instant Run dramatically speeds up your edit, build, and run cycles, keeping you "in the flow."

* **Robust and flexible build system:** Easily configure your project to include code libraries and generate multiple build variants from a single project. With Gradle, Android Studio offers high-performance build automation, robust dependency management, and customizable build configurations.

* **Develop for all Android devices:** Target multiple form factors with a single project to easily share code among your different versions of your app. Android Studio provides a unified environment to develop apps for Android phones, tablets, Android Wear, Android TV, and Android Auto.

* **Code templates and GitHub integration:** Start projects with code templates for patterns such as navigation drawer and view pagers, or import Google code samples from GitHub. Android Studio's project wizards make it easier than ever to add code in a new project.

### Choosing a Target Version

Before we start with the development of Android applications we will need to decide on which version of Android we will focus. For this it's best to take a look at which version is currently deployed on most devices. As can be seen in the chart below this would be version 6.0 or Marshmallow.

![Version Usage[^1]](img/version_usage.png)

[^1]: https://developer.android.com/about/dashboards/index.html

However our phones that we currently have at our disposal are equipped with Lollipop (version 5).

Taking both into consideration we will focus on Android 5.0. However nothing is holding us back to later on evolve to Marshmallow and try it out on a virtual device.

### Installing the SDKs

Before one can start with the development of applications for Android its necessary to install the correct SDKs (Software Development Kit). The Android SDK provides you with the API libraries and developer tools necessary to build, test, and debug apps for Android.

When launching Android Studio you will get presented with the welcome screen shown below. From here projects can be created, opened, imported, ... but also other Android Studio components can be launched.

![Welcome Screen of Android Studio](img/starting_as.png)

One of them is the SDK manager. To open the SDK manager select the "Configure" option at the bottom right corner and choose "SDK Manager".

The SDK manager will show the currently installed SDK versions.

Too allow us to develop for both Marshmallow and for Lollipop we will need to install both SDK versions. Check both API 21 and API 23 and hit the "Apply" button. Sit back for a minute as this will take some time.

<!-- TODO: Add screenshot -->

## Creating your first Android application

In this section we will create a simple "Hello World" Android application to get a hang of the flow of creating an application. You will learn how to create an Android project with Android Studio and run a debuggable version of the application inside a virtual device and on an actual phone. Let's get started.

### Creating a Project

Start by opening Android Studio. If you have no active projects you will get the following screen. Choose "Start a new Android Studio project" to launch the project wizard.

![Starting AS without an Active Project](img/starting_as.png)

If you have an active project in Android Studio you can always start a new project by navigating to "File => New Project".

The first thing you will need to do is give your application a **meaningful name**. Let's for example name it "HelloWorld". Also provide a company domain which will be used to build the package hierarchy in Java. A good example for this is `hello_world.nico.vives.be`. However you create your own. It follows the same format as a domain name.

> #### Info::Company Domain Name
> The domain name is used by Android Studio to generate a package name. Your package name is just a unique identifier for your application in the Google Play Store.
> It can be anything you want as long as it is unique. Generally, we use reverse domain names like *com.something*.

![Naming your Application](img/naming_project.png)

Next is to select our minimal target SDK. Just as the wizard states: "Low API levels target more devices, but offer fewer API features". This is because when features are added and you application needs to stay compatible with a lower version, most often these features will not be available for you. You need to make a decent decision here. Choosing a too low SDK version will not give you a lot of new features, but aiming to high will not allow most devices to run your application.

![Minimum SDK](img/target_sdk.png)

The next step consists of choosing a first activity (screen) for the application. More information on this later. Now you should select the "Basic Activity" to get a simple and basic screen with a single button on it. This does not force anything for the rest of your application. It just serves as a starting point.

> #### Info::Activity
> An **activity** represents a single screen with a user interface just like a window or frame.

![Activity Template](img/first_activity.png)

Last we need to give this first screen a name. This is actually the name of the class in Java that the activity will get. "MainActivity" is actually not such a bad name for your main application screen.

![Naming the Activity](img/naming_first_activity.png)

Once done, hit the finish button to launch the project view of your new application inside Android Studio.

### Creating a Virtual Device

Before we test our application on a physical device, it's a good idea to test it on a virtual device. In practice this is often done as not each Android developer has multiple devices at his disposal. Let us for example create a table device. Inside Android Studio navigate to "Tools => Android => AVD Manager", where AVD stands for Android Virtual Device.

![Android Virtual Device (AVD) Manager](img/avd_manager.png)

Start the AVD wizard by selecting "Create Virtual Device ...". First you need to select which type of device you would like to create. Since we have phones in the LAB, it would be useful to create a tablet device. Select the tablet category and choose a generic 10.1 inch tablet. Of course not all existing devices are available here as a predefined template. However using the "New Hardware Profile" option you can specify all the parameters of your virtual device. More on this later.

![AVD Device Type](img/avd_device_type.png)

Next the Android version needs to be specified for the device. Since the LAB smartphones are running Android 5.0.1, we will choose Marshmallow for our virtual device. This allows us to test our application with both Android versions on both a smartphone and a tablet. You will first need to download the image. This can be accomplished by selecting the "Download" option next to the name of the Android version.

![AVD Android Version for System Image](img/avd_version.png)

Give the AVD a decent name, as more will be created as we progress through this course. You can also set some other options such as the default startup orientation (portrait or landscape). You can also enable the device frame to show a realistic device frame around the emulator window.

![AVD Naming and Options](img/avd_name_options.png)

Feel free to create a new AVD later on and experiment with all the settings. Not much wrong you can do, chances of creating a black hole are slim at best.

One you click finish your new device should be available in the AVD manager.

![AVD Your Device Available](img/avd_new_available.png)

You can now close the AVD manager.

### Running the Application on a Virtual Device

When you want to run your application you have two options on how to run the app:
* **Run app**: (SHIFT-F10) this deploys the application on the device (virtual or not) and starts it. If anything goes wrong it just crashes. Not much you can do about it.
* **Debug app**: (SHIFT-F9) when running an application in debug mode, a special connection is made between your application and the IDE. This is typically called the attachment of a debugger. This allows you to monitor every step your application performs and even allows you to intervene. You can for example run parts of code line by line, or place a breakpoint where the application should pause until the debugger states it can continue (most often by your action as a programmer).

While developing applications we will most often start the app in debug mode. Even if we do not monitor it using the debugger. This because you will get a lot more information when the application crashes. This information is found in the debugger logs. But more on this later.

When you select to run your application (either in debug mode or normal mode) a window will appear asking on which device you wish to run the app. Since we do not have a physical device attached yet, we will only see the virtual tablet device.

<!-- TODO: What with devices with a lower API than minimum? Do they show up or are they hidden at that point ? -->

![Select an AVD](img/first_run_on_avd.png)

Select the device and hit OK. The virtual device should boot and your application should be started. Congrats you just ran your first virtual android application.

![Hello World on AVD](img/avd_hello_world.png)

Want to try something interactive? Hit the envelope at the bottom right corner.

See the action menu on the right of the AVD window? Try rotating the device.

> #### Info::Do not close the AVD
> You should not close the AVD window while developing. Otherwise the device is shut down and it needs to restart the next time you choose to run your application. Just minimize it to save time. If you change something in your application and you run it, it will be redeployed on the AVD.
