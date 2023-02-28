> **If you have CLion use it instead Visual Studio. In this tutorial we are using Visual Studio 2022, which implements some utilities about CMake.**  
  
Our project is based on CMakeLists which will define all our project settings. There is not .vcxproj Visual Studio project file, so you have to open the project in a different way.  

### 1 - Open Visual Studio App  
### 2 - Select "Open a local folder"
![Step1](uploads/0d6f77896739e71c33e83791c178e9fd/Step1.png)
### 3 - Select the project folder  
Even if Visual Studio does not display CMakeLists.txt files, it will detect them once a folder is opened with it.  

The Visual Studio interface should open, and this tab will appear :  
![CmakeLearn](uploads/888a8a8b2d7faf522da62990bc171ccd/CmakeLearn.png)  
You can ignore it. What you have to do is to verify if the CMakeLists generate the project properly.  
Here an exemple,   
**1** is the logger where the CMake generation will be printed,   
**2** the files hierarchy that is similar to file explorer view.  
![Structure](uploads/5069a10b1b01e021c4628e206cd0841a/Structure.png) 

If Visual Studio does not generate the project, you should enable CMake generation :  
![Step3](uploads/7aa780f7ad8c53999925b2939ca359cf/Step3.png)
Go to Project -> CMake Workspace Settings.  
Add and set "enableCMake" to true.  

### 4 - Build configurations

By default you just have a Debug build configuration, to add more: click on the configuration panel then on "Manage Configurations..."  
![buildConfig](uploads/48992bc7f6292b66d8989a4a021495dc/buildConfig.png)  
You just need to click on "Add a new configuration" and choose one in the list (preferably a x64 one). Be sure to have at least one debug and one release.  
![buildConfig2](uploads/b36e4611b0e46cdb0b6ae8c3fc50d069/buildConfig2.png)

### 5 - launch.vs.json  

Visual Studio will execute the project in the 'build' directory, but this is awkward if you are updating resources in runtime. To avoid this, we have to setup the working directory. In the hierarchy, right click on the main CMakeLists.txt, then select "open Debug and Launch settings".   
The file `launch.vs.json` will open in the IDE, all you have to do is to copy/paste the following code inside:
```
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "name": "Editor",
      "project": "CMakeLists.txt",
      "currentDir": "${workspaceRoot}",
      "buildConfigurations": [
        {
          "name": "Debug",
          "projectTarget": "Editor.exe (${workspaceRoot}\\build\\debug\\Editor.exe)",
          "project": "CMakeLists.txt",
          "args": [ "debug" ]
        },
        {
          "name": "Release",
          "projectTarget": "Editor.exe (${workspaceRoot}\\build\\release\\Editor.exe)",
          "project": "CMakeLists.txt",
          "args": [ "release" ]
        }
      ]
    }
  ]
}
```

If you don't see the "Debug and Launch settings" options you have to create the lauch.vs.json file: right click on the main CMakeLists.txt, then select "Add Debug Configuration".  
![AddDebug](uploads/d3a7329d56a2c1edd428d0440f4b03e9/AddDebug.png)  
Finally, select the default configuration. The wanted file is now created, next, you have to replace the file content with the code above.  

### 6 - Select a startup project  
The last thing to do is to select a startup project. If you have multiple project, only **"Editor.exe"** or **"Launcher.exe"** is interesting.   
![Step5](uploads/1201e3eb193a964ced85f3d7c4d764e1/Step5.png)  
Once you select a project, you can execute it as in standard Visual Studio project.  

[Home](Home.md)