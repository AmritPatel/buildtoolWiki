BuildConstants is a lightweight auto-generated class that can be used to access information about a build at runtime.

## Enums
The enums generated represent the full range of enabled build configurations, so that you can use them to easily test which configuration is active.

The default value for each of these is `None`, which is why this is also a reserved word that is not allowed to be used as a Release Type or Distribution name.

* `public enum ReleaseType`
* `public enum Platform`
* `public enum Architecture`
* `public enum Distribution`

## Current Configuration Info
These fields represent a full description of the current build. To simulate a specific build in the editor, select a build configuration in the "Build Configurations/Configurations" section of the UnityBuild editor window and then click `Refresh BuildConstants and Apply Defines` in "Build Configurations/Build Info".

* `public const string version` - This is the generated version string based on what's specified in "Product Parameters". If this is being used while running in the editor, this will just use the most recently generated string and will not auto-generate a new one.
* `public const ReleaseType releaseType`
* `public const Platform platform`
* `public const Architecture architecture`
* `public const Distribution distribution`