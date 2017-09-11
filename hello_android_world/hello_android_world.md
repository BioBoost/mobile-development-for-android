<!-- toc -->

# Hello Android World

Before we start with the development of Android applications we will need to decide on which version of Android we will focus. For this it's best to take a look at which version is currently deployed on the most devices. As can be seen in the chart below this would be version 6.0 or Marshmallow.

![Version Usage[^1]](img/version_usage.png)

[^1]: https://developer.android.com/about/dashboards/index.html

However our phones that we currently have at our disposal are equipped with Lollipop (version 5).

Taking both into consideration we will focus on Android 6.0 and make sure our apps are also compatible with Android 5.0.

## Android Studio

Android Studio is the official integrated development environment (IDE) for Google's Android operating system, built based on JetBrains' IntelliJ IDEA software and designed specifically for Android development. It is available for download on Windows, macOS and Linux based operating systems. It is a replacement for the Eclipse Android Development Tools (ADT) as primary IDE for native Android application development.

The current stable version is 2.3.3, released in June 2017. Next major update, version 3.0, is in preview stage as of August 2017. Since we love working on the edge, we will be using the preview version, eagerly awaiting the stable release of it. Navigate to (https://sillevl.gitbooks.io/software-installation-guide)[https://sillevl.gitbooks.io/software-installation-guide] and follow the installation guide to install the latest Android Studio 3.0 version.

### Some cool features

* **Instant Run:** Push code and resource changes to your app running on a device or emulator and see the changes instantly come to life. Instant Run dramatically speeds up your edit, build, and run cycles, keeping you "in the flow."

* **Intelligent code editor:** Write better code, work faster, and be more productive with an intelligent code editor that helps you each step of the way. Android Studio is built on IntelliJ and is capable of advanced code completion, refactoring, and code analysis.

* **Fast and feature-rich emulator:** Install and run your apps faster than with a physical device and test your app on virtually any Android device configuration: Android phones, Android tablets, Android Wear, and Android TV devices. The new Android Emulator 2.0 is faster than ever and allows you to dynamically resize the emulator and access a suite of sensor controls.

* **Robust and flexible build system:** Easily configure your project to include code libraries and generate multiple build variants from a single project. With Gradle, Android Studio offers high-performance build automation, robust dependency management, and customizable build configurations.

* **Develop for all Android devices:** Target multiple form factors with a single project to easily share code among your different versions of your app. Android Studio provides a unified environment to develop apps for Android phones, tablets, Android Wear, Android TV, and Android Auto.

* **Code templates and GitHub integration:** Start projects with code templates for patterns such as navigation drawer and view pagers, or import Google code samples from GitHub. Android Studio's project wizards make it easier than ever to add code in a new project.

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
