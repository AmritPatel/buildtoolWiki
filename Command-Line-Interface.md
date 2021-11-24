At the moment, command line functionality is minimal, but it will be improved over time.

### Basic Usage

Open a terminal or command prompt in your Unity project's directory. Then, start Unity in batch mode and direct it to execute SuperUnityBuild's command line interface build function.

```shell
# OSX
cd ~/Documents/MyUnityProject
/Applications/Unity/Hub/Editor/YourEditorVersion/Unity.app/Contents/MacOS/Unity -quit -batchmode -executeMethod SuperUnityBuild.BuildTool.BuildCLI.PerformBuild

# Windows
cd C:/Users/Me/Documents/MyUnityProject
"C:\Program Files\Unity\Editor\Unity.exe" -quit -batchmode -executeMethod SuperUnityBuild.BuildTool.BuildCLI.PerformBuild
```

For general information about running Unity at the command line see [[https://docs.unity3d.com/Manual/CommandLineArguments.html]]
