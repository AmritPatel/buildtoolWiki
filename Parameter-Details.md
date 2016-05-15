## Basic Settings

#### Build Path Options
**Base Build Folder** - The base path where all builds will be output. Relative or absolute path. Relative paths are relative to the unity project's base folder.

**Build Path** - The path for each new build. If the path isn't unique, the previous build will be deleted. Recognized tokens for the build path:
* `$YEAR`
* `$MONTH`
* `$DAY`
* `$TIME`
* `$RELEASE_TYPE`
* `$PLATFORM`
* `$ARCHITECTURE`
* `$DISTRIBUTION`
* `$VERSION`
* `$BUILD`

#### Post-Build Options
**Open output folder after build** - Opens the base build folder after the build completes.



## Product Parameters

**Version** - The version number/string for the build. Recognized tokens for the version:
* `$ADJECTIVE` - A randomly selected adjective.
* `$NOUN` - A randomly selected noun.
* `$DAYSSINCE` - The number of days since a specified date. For example, `DAYSSINCE("January 1, 2015")`.
* `$SECONDS` - The number of seconds since midnight, divided by 15 (an arbitrarily selected divisor just to keep the number a reasonable length).
* `$BUILD` - The build count number.

**Build Count** - A counter that increments ever time a build is performed. Click the "Reset" button to reset the value to zero.



## Release Types

## Build Platforms