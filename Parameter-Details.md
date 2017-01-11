## Basic Settings

![](https://raw.githubusercontent.com/Chaser324/unity-build/gh-pages/Unity_2017-01-11_00-01-24.png)

#### Build Path Options
**Base Build Folder** - The base path where all builds are created. Click the "..." button to set this value. If working in a team, a path within the Unity project folder (but not in Assets) works best so that it will resolve to the same location for everyone.

**Build Path** - The path for each new build. If the path isn't unique, the previous build will be deleted and overwritten. Recognized tokens for the build path:
* `$YEAR` - The current year in "yyyy" format. 
* `$MONTH` - The current month in "MM" format.
* `$DAY` - The current day in "dd" format.
* `$TIME` - Current time in "hhmmss" format.
* `$RELEASE_TYPE` - The release type name.
* `$PLATFORM` - The build platform (PC, OSX, Linux,...)
* `$ARCHITECTURE` - The build architecture (x86, x64,...).
* `$DISTRIBUTION` - The build distribution name.
* `$VERSION` - The specified version for this build.
* `$BUILD` - The build count number, shown in the product parameter settings.
* `$PRODUCT_NAME` - The product name specified in the [ReleaseType](#release-types).

#### Post-Build Options
**Open output folder after build** - Opens the base build folder after the build completes.




## Product Parameters

![](https://raw.githubusercontent.com/Chaser324/unity-build/gh-pages/Unity_2017-01-11_00-01-24-2.png)

**Version** - The version number/string for the build. Recognized tokens for the version:
* `$ADJECTIVE` - A randomly selected adjective.
* `$NOUN` - A randomly selected noun.
* `$YEAR` - The current year in "yyyy" format. 
* `$MONTH` - The current month in "MM" format.
* `$DAY` - The current day in "dd" format.
* `$TIME` - Current time in "hhmmss" format.
* `$DAYSSINCE` - The number of days since a specified date. For example, `$DAYSSINCE("January 1, 2015")`.
* `$SECONDS` - The number of seconds since midnight, divided by 15 (an arbitrarily selected divisor just to keep the number a reasonable length).
* `$BUILD` - The build counter number.

**Auto-Generate Version** - If enabled, the version string will be generated every time a build is performed. Otherwise, the version string will only be updated when the "Generate Version String Now" button is clicked.

**Build Counter** - A counter that increments every time a build is performed. Can be manually set to a value or automatically reset by clicking the "Reset Build Counter" button.




## Release Types

![](https://raw.githubusercontent.com/Chaser324/unity-build/gh-pages/Unity_2017-01-11_00-01-42.png)

Release types are intended to provide some top level separation between different versions of your game. For example, you might create "Release" and "Demo" release types or a release type for different languages you're distributing.

**Add Release Type** - Adds a new release type.

#### Basic Info
**Type Name** - The name of this release type.

**Bundle Identifier** - The bundle identifier used for an iOS/Android build. This corresponds to [Application.bundleIdentifier](http://docs.unity3d.com/ScriptReference/Application-bundleIdentifier.html) and the "Bundle Identifer" setting in the iOS/Android [Player Settings](http://docs.unity3d.com/Manual/class-PlayerSettingsiOS.html).

**Product Name** - The product name used for the build. This corresponds to [Application.productName](http://docs.unity3d.com/ScriptReference/Application-productName.html) and the "Product Name" setting in [Player Settings](http://docs.unity3d.com/Manual/class-PlayerSettings.html)

#### Build Options
**Custom Defines** - Custom pre-processor defines that will be used when compiling builds under this Release Type. Lists should be comma or semicolon delimited.

**Development Build** - If enabled, all builds under this release type will be development builds. This corresponds to the "Development Build" option in [Build Settings](https://docs.unity3d.com/Manual/BuildSettings.html) and [BuildOptions.Development](https://docs.unity3d.com/ScriptReference/BuildOptions.Development.html).

**Script Debugging** - If enabled, all builds under this release type will allow script debugging. The above "Development Build" setting must also be enabled for this to do anything. This corresponds to the "Script Debugging" option in [Build Settings](https://docs.unity3d.com/Manual/BuildSettings.html) and [BuildOptions.AllowDebugging](https://docs.unity3d.com/ScriptReference/BuildOptions.AllowDebugging.html).

**Delete** - Deletes this release type.

#### SceneList
This is the list of scenes that will be included in the build. The order they appear is the order in which they're included, so the scene at the top will be the first scene loaded.

The arrow keys will adjust the position of a scene in the list, with the double-up arrow moving a scene directly to the top of the list. The "X" button will remove a scene from the list.

**Refresh Scene List** - Refreshes the list of scenes available to add by searching through all assets.




## Build Platforms

![](https://raw.githubusercontent.com/Chaser324/unity-build/gh-pages/Unity_2017-01-11_00-07-02.png)

Build platforms are used to specify targeted hardware configurations. Distributions can optionally be specified to provide an additional layer of granularity in your builds such as distinguishing between different release storefronts (Steam, itch.io, direct download, etc.).

**Add Platform** - Adds the selected platform to your set of targeted platforms.

#### Build Platform Settings
**Architectures** - If a build platform has multiple architectures, you can select the architectures you wish to target and build here.

**Add Distribution** - Create a new distribution. You can then specify a name for the distribution, enable/disable it, or delete it by clicking the "X" button next to it.

**Delete** - Remove this platform from your set of targeted hardware platforms.



## Pre/Post-Build Actions

![](https://raw.githubusercontent.com/Chaser324/unity-build/gh-pages/Unity_2017-01-11_00-10-00.png)




## Build Configurations

![](https://raw.githubusercontent.com/Chaser324/unity-build/gh-pages/Unity_2017-01-11_00-07-23.png)

A Build Configuration is a full representation of a build constructed from Release Type, Platform, Architecture, and Distribution.

#### View Options
**Hide disabled configurations** - Hides all disabled build configurations in the "Configurations" section below.

**Show full configurations tree** - Enables tree view for the "Configurations" section below. Tree view is helpful for visualizing all build configuration options and easily enabling/disabling entire groups.

#### Configurations
A full display of all build configurations.

In the default view, you can enable/disable individual build configurations so that they won't be included when clicking the "Perform All Enabled Builds" button. In the tree view (enabled above in "View Options"), you can enable/disable entire groups of build configurations.

Clicking on a build configuration in this view will display its info in the "Build Info" section below and allow you to perform a build of just that specific configuration, as well as allowing you to simulate the use of that configuration in the editor.

#### Build Info
This displays all relevant information about a build configuration selected from the "Configurations" section above.

**Build** - Builds the selected build configuration.

**Build and Run** - Builds the selected build configuration and then automatically launches it.

**Build and Run w/ Profiler** - Builds the selected build and the automatically launches it and connects the profiler. This is only available if "Development Build" is enabled in this build configuration.

**Refresh BuildConstants and Apply Defines** - Generates the [[BuildConstants]] class and applies all of the defines listed above. This is useful for simulating the characteristics of a specific build configuration when running inside the Unity Editor.
