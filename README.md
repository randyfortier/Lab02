# Lab 01
The starter code for lab 01.

## Part 1
For the first part of this lab, you will install some software that we will use throughout this course.  Additional instructions for installation in various editors can be found at the following location:
- https://flutter.dev/docs/get-started/install

### Installing the Flutter SDK
First, we need to install the Flutter SDK.  This includes the Flutter development toolchain, including the builder, the engine, and the command line tools.  Download and install this SDK from the following location:
- https://flutter.dev/docs/get-started/install

### Installing Android Studio/Android SDK
Next, we need to install Android Studio.  Even if you do not want to use Android Studio for development, you need the Android SDK that it installs.

#### Windows, Linux, and MacOS Users:
You can download and install an Android Studio installer from the following location: 
- https://developer.android.com/studio

_**Note:**  A commercial (but free) IDE, IntelliJ, is also available with Android/Flutter support.  If you want to try this, instead, download it from the following location:_
- https://www.jetbrains.com/idea/download

Follow the installation prompts to install Android Studio (or IntelliJ).  Next, we'll need to install the Flutter plug-in, which allows the creation and execution of Flutter projects from within Android Studio (or IntelliJ).

#### Windows and Linux Users:
In the `File` menu, select `Settings`.  Choose `Plugins` on the left, find the `Flutter` plug-in, and install it.  The `Dart` plug-in will also need to be installed, as the `Flutter` plug-in depends on it.  You will need to restart Android Studio.

#### MacOS Users:
In the `Preferences` menu, select `Plugins`.  Find the `Flutter` plug-in, and install it.  The `Dart` plug-in will also need to be installed, as the `Flutter` plug-in depends on it.  You will need to restart Android Studio.

_**Note:**  Installation of the Flutter plug-in for IntelliJ is very similar._

### Installing an Android Platform
Run Android Studio, and select SDK Manager from the Tools menu.  On the left, select Appearance & Behavior -> System Settings -> Android SDK.  From the list, choose a version of Android that you'd like to use when running your applications.  It is recommended that you avoid any pre-release versions, as development tools for those versions are often buddy and unsupported.  It is also recommended that you choose a relatively recent version, since they usually provide a better experience (for developers and users).

_**Note:** Even though we are using Android Studio (or IntelliJ) for this step, using a programmer's text editor still requires that you install the version of Android you will use, and creating a virtual device (in the next step).  Don't skip this step if you intend to use VS Code._

_**Note:**  MacOS users have the option to deploy their projects to the iOS simulator.  To do this, first install Xcode.  MacOS users can run either Android or iOS.  Windows and Linux users cannot deploy to iOS, neither through the simulator nor a real device.  Even if running on iOS, it is recommended that you test all of your apps on Android to ensure they also work on that platform, since the markers will all be using Android._

### Creating an Android Virtual Device (AVD)
Finally, we need to create a virtual device (emulator) to use when running our future projects.  Select AVD Manager from the Tools menu.  Click the Create Virtual Device… button.  The specifications are up to you; some people create a device identical to their personal device (if you have one).  Ensure that the device is relatively new, though, so that it can run the newer version of Android that you've downloaded.

That was it, you can now shut down Android Studio (or IntelliJ) and move onto the next step.  If you want to use Android Studio/IntelliJ, you can use the menus to create a new Flutter project (after the IDE has restarted).  Even if you don't plan to use it, it is a good idea to try it out.  You can also run your newly created AVD by clicking the play button in the AVD Manager window.

### Installing a Text Editor
You should also install a text editor.  This is very personal, and you are welcome to use any text editor that you wish, but it is advisable to choose a text editor that has syntax highlighting for Dart.  Some popular text editors include:
- VS Code:	https://code.visualstudio.com/download  
- Atom:  	http://atom.io 
- Brackets:	http://brackets.io 
- Sublime:	https://www.sublimetext.com/ (not free)

In this lab, we'll be using Visual Studio Code.  The instructor will also be using VS Code in the lectures because it provides a better developer experience.  Therefore, these instructions are for VS Code.  If you use any other text editor, you'll most likely be using the command line as there likely is not a Flutter plug-in for it.

Start Visual Studio Code, and select Command Palette… from the View menu.  In the command palette that pops up, choose Extensions: Install Extensions.  Select the Flutter plug-in, and install it.  The Dart plug-in will also be installed, since the Flutter plug-in depends on it.

## Part 2
Now that we have the software that we need, let's write your own app in Flutter.  These instructions are for VS Code.  If using Android Studio or IntelliJ, the New Project menu item will have a Flutter option, and it relatively straightforward.

### Creating and Running a Flutter Project Using the Command Line
Create a new directory/folder where you'd like your CSCI 4100U labs to be created.  Open a terminal/command prompt (use CTRL-Shift-C in VS Code), and navigate to that directory (an example is included, below).  Use the command flutter create lab01 to create a new Flutter project.

```
$ mkdir -p ~/csci4100u/labs
$ cd ~/csci4100u/labs
$ flutter create lab01
Creating project lab01...
  lab01\.gitignore (created)
  lab01\.idea\libraries\Dart_SDK.xml (created)
  …
  lab01\test\widget_test.dart (created)
Running "flutter pub get" in lab01...                               3.5s
Wrote 66 files.

All done!
[√] Flutter is fully installed. (Channel stable, v1.7.8+hotfix.4, on Xubuntu [Version 3.6.18], locale en-US)
[!] Android toolchain - develop for Android devices is partially installed; more components are available. (Android SDK version 29.0.1)
[√] Android Studio is fully installed. (version 3.5)
[√] IntelliJ IDEA Community Edition is fully installed. (version 2017.3)
[√] VS Code, 64-bit edition is fully installed. (version 1.37.1)
[√] Connected device is fully installed. (1 available)

Run "flutter doctor" for information about installing additional components.
```

In order to run your application, type:

```
  $ cd lab01
  $ flutter run
```

Your application code is in `lab01\lib\main.dart`.

After creating your project, the flutter command does a quick environment check to ensure that you have everything setup correctly.  Yours may look different, but look for any failed tests to diagnose.  To run a more complete diagnostic, use the flutter doctor command:

```
$ flutter doctor

Doctor summary (to see all details, run flutter doctor -v):
[√] Flutter (Channel stable, v1.7.8+hotfix.4, on Xubuntu [Version 3.6.18], locale en-US)
[!] Android toolchain - develop for Android devices (Android SDK version 29.0.1)
    X Android license status unknown.
      Try re-installing or updating your Android SDK Manager.
      See https://developer.android.com/studio/#downloads or visit https://flutter.dev/setup/#android-setup for detailed instructions.
[√] Android Studio (version 3.5)
[√] IntelliJ IDEA Community Edition (version 2017.3)
[√] VS Code, 64-bit edition (version 1.37.1)
[√] Connected device (1 available)

! Doctor found issues in 1 category.
```

Above you can see a common issue with Android licensing.  This is a known issue, and you may or may not experience it on your own system.  You can still run Flutter projects, even with this error.

Finally, let's run our new application:

```
$ cd lab01
$ flutter run
```

_**Note:**  The biggest advantage of running in the Terminal/Command Prompt is that you can manually hot reload the application, which is necessary when some changes are made to the code._

### Creating and Running a Flutter Project Within VS Code
Create a new Flutter project, called lab01b, by selecting `Command Palette…` from the `View` menu, and typing `Flutter: New Project`.  Next, run your AVD by selecting `Command Palette…` from the `View` menu, and typing `Flutter: Launch Emulator`.    Finally, run the project using Start Debugging from the Debug menu (or `F5`).  VS Code will give you the option to open the Dev Tools web page.  It is recommended that you do, so that you can explore the widget tree while debugging.

Regardless of which way you created the project, run the application, and explore the code in `lib/main.dart`.

## Getting Help
If you run into difficulty, you may wish to check out some of the following resources:

- https://api.flutter.dev/  - The standard documentation for Flutter, all classes and methods.
- https://dart.dev/tutorials - A series of tutorials for the Dart programming language, focusing entirely on the features of Dart.
- https://flutter.dev/docs/reference/tutorials - A series of tutorials for the Flutter platform, focusing mainly on the widgets and API.
- https://flutter.dev/docs/codelabs - A series of deep-dive, more comprehensive, tutorials to learn more about the Flutter platform.
- https://flutter.dev/docs/cookbook - A set of recipes for commonly used features of Flutter.
- https://github.com/flutter/samples/blob/master/INDEX.md - A repository containing some completed Flutter applications.
- http://stackoverflow.com/ - A forum for asking questions about programming.  I bet you know this one already!

Of course, you can always ask the TA for help!  However, learning how to find the answers out for yourself is not only more satisfying, but results in greater learning as well.

## How to Submit
Create your flutter projects inside this folder, commit, and then push your code to this repository to submit your lab assignment.