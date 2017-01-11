# Basic Setup
This is the minimum number of steps to go from zero to building.

* Import SuperUnityBuild into your project. See [[Installation]] for more info.
* Open the SuperUnityBuild window by clicking `Window > SuperUnityBuild` in the Unity menu bar.
* Click `Release Types` and then click the `Add Release Type` button. Set a `Type Name` ("Release" is a good option for now if you want to get going quickly) and modify the `Product Name` if you want it to differ from what you have set in Unity's Player Settings.
* Still looking at your added Release Type, click `SceneList` and then add/order the scenes you want in the build, the scene at the top of the list will be loaded first.
* Click `Build Platforms`, select a platform you want to build and then click the `Add Platform` button. In the newly added Build Platform, select the specific architectures you want to build. Repeat for any additional platforms you want.
* Click the big green `Perform All Enabled Builds` button. You're now building with SuperUnityBuild!

# Basic Customization
As a next step, you may want to start customizing your build output a bit.

* In `Basic Settings` you can setup where the build output is placed. Consult [[Basic Settings|Parameter-Details#basic-settings]] for info on all of the recognized path tokens. Keep in mind that if the path isn't unique, the previous build will be overwritten. In some cases, this may be what you want, but the path tokens will allow you to customize it as you see fit.
* In `Product Parameters` you can setup version number generation. At runtime, you can access this version string and other build info through [[BuildConstants]] which can be very useful for displaying version info on screen or performing different behavior based on the platform, architecture, distribution platform, etc.
* In `Release Types`, add additional release types that make sense to distinguish different versions of your game. You may want a "Development" Release Type with the development and debugging options enabled or perhaps a "Demo" Release Type that includes a limited set of scenes.
* In `Build Platforms`, clicking the `Add Distribution` will add another level of granularity to your builds. This is generally intended for setting up different builds for different distribution platforms (Humble Bundle, Steam, itch.io, App Store, etc.), but there are numerous other ways you could choose to use it.
* In `Pre-Build Actions` and `Post-Build Actions` you can add additional operations to your build workflow outside of just building the executable. None are included in the base install of SuperUnityBuild, but take a look at the [Unity-Build-Actions](https://github.com/Chaser324/unity-build-actions) repository for a collection of some useful ones. Refer to each BuildAction's README for specific info on its settings. Speaking generally, build actions can be used to do things like create a zip file of your build, update AssetBundles, move/copy/delete files, or upload to distribution platforms - things that may typically make your build process cumbersome and difficult - and do it all automatically with each build.
* In `Build Configurations`, you can enable/disable build configurations to include in your batch build - you probably don't want to build every version of your game every time. There are also options here to view info about each configuration or to perform a build of just one specific build configuration. 


