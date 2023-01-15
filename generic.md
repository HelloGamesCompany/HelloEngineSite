---
layout: post
title: Scripting System
description: Lorem ipsum dolor est
nav-menu: true
---

<video width="320" height="240" controls>
  <source src="assets/videos/HelloEngineDemo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<div style="text-align: justify;">Hello Engine includes a C++ Scripting system, using Hot Reload and Automatic Compilation. You can use C++ code to create behavior scripts, that can then be added to any Game Object. This behaviors get Started and Updated once the Play button is pressed.
This works using Visual Studio 2019.</div><br>
**Automatic Compilation**  

This is an optional feature, enabled by default, that compiles the Scripting project when:

* A new script has been added.
* A script has been modified.

<div style="text-align: justify;">Compilation may fail. If that happens, the automatic compilation will not let the Hot Reload system to apply any changes. When compilation fails, the user must go to the Scripting solution and fix any compilation errors. Then, the automatic compilation will detect changes on a script, and try compiling again. Automatic compilation occurs only when the Hello Engine window is focused.</div><br>
**Hot Reload** 

When the Scripting project is Compiled, the Hello Engine code will know about it, and try to replace the old DLL file containing the scripting code with the new one. This process consists of:
* Destroying all DLL information
* Freeing the DLL from memory using FreeLibrary
* Replacing the old DLL with the new one.
* Loading the DLL into memory using LoadLibrary
* Creating all necessary information again.

This is done during runtime so the engine can remain opened in the process.

**Creating and using Scripts** 

<div style="text-align: justify;">To create a Script, is best to create it from the Project Window inside Hello Engine. Choose a name for the script, and it will be created and automatically added into the Scripting project.
If automatic compilation is enabled, the Scripting project will be compiled. If not, you won’t be able to use the added script until manually compiling the project.<br><br>

The scripts created are classes that inherit from a HelloBehavior abstract class. Any script that doesnt inherit from HelloBehavior cannot be dragged into a Script Component later on.<br><br>

To edit the script, go to the Scripting solution, and use it to edit anything you need. Save your changes. If automatic compilation is enabled, the project will be compiled once you enter the Hello Engine window. If not, remember to manually compile to apply your changes.<br><br>

To use the script, create a Game Object and add a Script Component to it. Then, drag the created script (either the .cpp or .h file) to the Script Component in the Inspector window. When the Play button is pressed, the script will start executing its behavior.<br><br>

You can add the script member variables to the Script Component inspector window, so they can be edited in the Hello Engine window. Available inspector values include: int, float, std::string, bool, GameObject, Transform and Mesh Renderer components. </div><br>
**Play / Pause / One Frame / Stop** 

<div style="text-align: justify;">Once the Play buton is pressed, all Start() methods of every HelloBehavior script attached to a ScriptComponent will be called. Every frame from then, the Update() method will be called. 
The Scene gets internally serialized, to recover its state once the Stop button is pressed.</div><br>
If pressed pause, the Update() methods won’t be called.

If pressed One Frame (during Pause), the Update() methods will be called once, and then stop again.

If pressed Stop, all HelloBehaviors will stop updating and the scene will serialize to the state prior to pressing the Play button.

