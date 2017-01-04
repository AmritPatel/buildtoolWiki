## Basic Settings

#### Build Path Options
**Base Build Folder** - The base path where all builds will be output. Relative or absolute path. Relative paths are relative to the unity project's base folder.

**Build Path** - The path for each new build. If the path isn't unique, the previous build will be deleted. Recognized tokens for the build path:
* `$YEAR` - The current year in "yyyy" format. 
* `$MONTH` - The current month in "mm" format.
* `$DAY` - The current day in "dd" format.
* `$TIME` - Current time in "hhmmss" format.
* `$RELEASE_TYPE` - The release type name.
* `$PLATFORM` - The build platform (PC, OSX, Linux,...)
* `$ARCHITECTURE` - The build architecture (x86, x64,...).
* `$DISTRIBUTION` - The build distribution name.
* `$VERSION` - The specified version for this build.
* `$BUILD` - The build count number, shown in the product parameter settings.

#### Post-Build Options
**Open output folder after build** - Opens the base build folder after the build completes.



## Product Parameters

**Version** - The version number/string for the build. Recognized tokens for the version:
* `$ADJECTIVE` - A randomly selected adjective.
* `$NOUN` - A randomly selected noun.
* `$YEAR` - The current year in "yyyy" format. 
* `$MONTH` - The current month in "mm" format.
* `$DAY` - The current day in "dd" format.
* `$TIME` - Current time in "hhmmss" format.
* `$DAYSSINCE` - The number of days since a specified date. For example, `$DAYSSINCE("January 1, 2015")`.
* `$SECONDS` - The number of seconds since midnight, divided by 15 (an arbitrarily selected divisor just to keep the number a reasonable length).
* `$BUILD` - The build count number.

**Build Count** - A counter that increments ever time a build is performed. Click the "Reset" button to reset the value to zero.



## Release Types

Release types are intended to provide some top level separation between different versions of your game. For example, you might create "Release" and "Demo" release types or a release type for different languages you're distributing.

**Add Release Type** - Adds a new release type.

#### Release Type
**Type Name** - The name of this release type.

**Bundle Identifier** - The bundle identifier used for an iOS/Android build. This corresponds to [Application.bundleIdentifier](http://docs.unity3d.com/ScriptReference/Application-bundleIdentifier.html) and the "Bundle Identifer" setting in the iOS/Android [Player Settings](http://docs.unity3d.com/Manual/class-PlayerSettingsiOS.html).

**Product Name** - The product name used for the build. This corresponds to [Application.productName](http://docs.unity3d.com/ScriptReference/Application-productName.html) and the "Product Name" setting in [Player Settings](http://docs.unity3d.com/Manual/class-PlayerSettings.html)

## Build Platforms

Build platforms are used to specify targeted hardware configurations. Distributions can optionally be specified to also allow an additional layer of granularity in your builds such as distinguishing between different release storefronts (Steam, itch.io, direct download, etc.).

**Add Platform** - Adds the selected platform to your set of targeted platforms.

#### Build Platform Settings
**Architectures** - If a build platform has multiple architectures, you can select the architectures you wish to target and build here.

**Add Distribution** - Create a new distribution. You can then specify a name for the distribution, enable/disable it, or delete it by clicking the "X" button next to it.

**Delete** - Remove this platform from your set of targeted hardware platforms.



## Build Configurations

#### View Options

#### Configurations

#### Build Info