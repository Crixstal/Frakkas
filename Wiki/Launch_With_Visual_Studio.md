> **If you have CLion use it instead Visual Studio. In this tutorial we are using Visual Studio 2022, which implements some utilities about CMake.**  
  
Our project is based on CMakeLists which will define all our project settings. There is not .vcxproj Visual Studio project file, so you have to open the project in a different way.  

### 1 - Open Visual Studio App  
### 2 - Select "Open a local folder"
<img src="https://user-images.githubusercontent.com/91843760/221991381-13c7f688-aa03-482d-b571-5d9e7bbee088.png" width=75% height=75%>  

### 3 - Select the project folder  
Even if Visual Studio does not display CMakeLists.txt files, it will detect them once a folder is opened with it.  

The Visual Studio interface should open, and this tab will appear :  
<img src="https://user-images.githubusercontent.com/91843760/221991639-9b295bdf-190e-49de-ac2b-69afa4560aa2.png" width=75% height=75%>  
You can ignore it. What you have to do is to verify if the CMakeLists generate the project properly.  
Here an exemple,   
**1** is the logger where the CMake generation will be printed,   
**2** the files hierarchy that is similar to file explorer view.  
<img src="https://user-images.githubusercontent.com/91843760/221991823-add1d1bb-a638-49ad-9aec-e2f29b8cca40.png" width=75% height=75%>    
If Visual Studio does not generate the project, you should enable CMake generation :  
<img src="https://user-images.githubusercontent.com/91843760/221991914-61e1e7d1-03ba-405e-82b8-470100fb25de.png" width=75% height=75%>  
Go to Project -> CMake Workspace Settings.  
Add and set "enableCMake" to true.  

### 4 - Build configurations

By default you just have a Debug build configuration, to add more: click on the configuration panel then on "Manage Configurations..."  
<img src="https://user-images.githubusercontent.com/91843760/221992099-f8904089-7b1b-479a-ae09-535045c8c75a.png" width=25% height=25%>  

You just need to click on "Add a new configuration" and choose one in the list (preferably a x64 one). Be sure to have at least one debug and one release.  
<img src="https://user-images.githubusercontent.com/91843760/221992110-15a1c136-82d3-48e4-b800-f46f3c5cfd32.png" width=75% height=75%>  

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
<img src="https://user-images.githubusercontent.com/91843760/221992269-3396ea82-23c0-4070-acfd-e2071b19bd01.png" width=75% height=75%>  
Finally, select the default configuration. The wanted file is now created, next, you have to replace the file content with the code above.  

### 6 - Select a startup project  
The last thing to do is to select a startup project. If you have multiple project, only **"Editor.exe"** or **"Launcher.exe"** is interesting.   
<img src="https://user-images.githubusercontent.com/91843760/221992283-d9290d2f-be9f-4149-9577-82355591a3fe.png" width=75% height=75%> 

Once you select a project, you can execute it as in standard Visual Studio project.  

[Home](README.md)
