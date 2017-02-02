BuildActions allow you to expand the functionality of SuperUnityBuild by adding new methods that can run before/after all builds or the individual builds of each separate configuration. If you need some examples, check out the [unity-build-actions](https://github.com/Chaser324/unity-build-actions) repository.

## Standard BuildAction Options

While each BuildAction will have its own set of options related to whatever purpose it serves, there are a few options that are common to most of them.

* **Action Type** - This option is used to select whether a BuildAction should run once before/after all builds in a batch ("Single Run") or before/after each individual build in a batch ("Per Platform"). 
* **Filter** - The filter is used to limit the build configurations where a BuildAction should execute. For example, if you have a BuildAction that zips up your builds, but you only want it to run if it's a release build for Humble Bundle. You might do something like this:

![](https://raw.githubusercontent.com/Chaser324/unity-build/gh-pages/Unity_2017-01-11_21-18-05.png)

## Creating a BuildAction

To create a new BuildAction:
* Create a class that inherits from `BuildAction`.
* Override `Execute` and/or `PerBuildExecute` with your new functionality. As the names and method signatures imply, the `Execute` method is intended to run before/after all builds and `PerBuildExecute` will run before/after each individual build.
* Implement one or more of the following interfaces: `IPreBuildAction`, `IPreBuildPerPlatformAction`, `IPostBuildAction`, `IPostBuildPerPlatformAction`. There's nothing to actually implement with any of them. SuperUnityBuild just uses it to identify where your BuildAction is allowed to be used. If you don't implement at least one of these, you won't see your BuildAction available for selection in SuperUnityBuild.
* If you need to customize the inspector appearance, override `DrawProperties`. Be aware when doing this that if you call `base.DrawProperties`, it will be unaware of which properties you've already displayed and this may cause properties to appear twice. In this case, it's recommended to either draw all of the property fields yourself and not call `base.DrawProperties` or apply the [HideInInspector] attribute to any properties that you show yourself as this will cause the base class to not automatically draw fields for them.

When implementing your new functionality, `BuildProject` has several static helper methods that you may find useful:
* `ResolvePath` - Resolves the standard set of path tokens ($RELEASE_TYPE, $PLATFORM, etc.) in a given string.
* `SanitizeCodeString` - Sanitizes a string for use in code. For example, the [[BuildConstants]] code generator uses this to convert ReleaseType, Platform, Architecture, and Distribution names into a form that is safe for use as a pre-processor define or variable name.
* `SanitizeFolderName` - Sanitizes a string for valid use as a folder name.
* `SanitizeFileName` - Sanitizes a string for valid use as a file name.
