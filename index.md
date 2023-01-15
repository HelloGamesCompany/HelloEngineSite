---
title: HELLO ENGINE 
layout: landing
description: 'A C++ / OpenGL Game Engine made by video game development students Zhida Chen & Adrià Sellarés. 

Hello Engine is a fully featured game engine for Windows platform, with Level Editor, Entity Component System, Custom File Format, Scripting system, Undo/Redo, Resource Manager, Serialization system, and many others.

This was a university assignment made in 3~ months.'

image: assets/images/pic07.jpg
nav-menu: true
---

<!-- Main -->
<div id="main">

<!-- Two -->
<section id="two" class="spotlights">
	<section>
		<img class = "avatar-image" src="{% link assets/images/Chen.jpg %}" alt="" data-position="center center" />
		<div class="content" style="width:450px !important">
			<div class="inner">
				<header class="major">
					<h3>Zhida Chen</h3>
				</header>
				<ul>
  					<li>File system</li>
  					<li>Undo/Redo system</li>
  					<li>Collaborated on Serialize scene</li>
					<li>Collaborated on GameObject</li>
					<li>Collaborated on Scripting system</li>			
					<li>Other miscellaneous tasks</li>
					<li>Website Creation</li>
				</ul>
				<ul class="actions">
					<a href="https://github.com/Xidashuaige" target="_blank" class="button">GitHub</a>
					<a href="https://www.linkedin.com/in/zhida-chen-06940b1a9" target="_blank" class="button">Linkedin</a>
				</ul>
			</div>				
		</div>
		<img class = "avatar-image" src="{% link assets/images/Adria.jpg %}" alt="" data-position="center center" />	
		<div class="content" style="width:450px !important">
			<div class="inner">
				<header class="major">
					<h3>Adriá Sellarès</h3>
				</header>
				<ul>
  					<li>Rendering System with OpenGL</li>
  					<li>Custom File Format</li>
  					<li>Entity Component System</li>
					<li>Hot Reload & Inspector Fields</li>
					<li>Time Management</li>
					<li>Collaborated on Resource Manager, Scripting, Serialization</li>
				</ul>
				<ul class="actions">
					<a href="https://github.com/AdriaSeSa" target="_blank" class="button">GitHub</a>
					<a href="https://www.linkedin.com/in/adria-sellares" target="_blank" class="button">Linkedin</a>
				</ul>
			</div>		
		</div>		
	</section>
	<section>
		<img class = "image" src="{% link assets/images/LevelEditor.png %}" alt="" data-position="center center" />
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Level Editor</h3>
				</header>
				<p class="text-align">A Scene camera shows the 3D scene currently being edited. You can edit all object’s position, rotation and scale using a gizmo. You can also pick any object from the scene by clicking on it on the Scene Window (this has been done using a Raycast).</p>
			</div>
		</div>
	</section>
	<section>
		<img class = "image" src="{% link assets/gifs/entityComponent.gif %}" style="transform:translateY(50%)" alt="" data-position="25% 25%" />
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Entity Component System</h3>
				</header>
				<p class="text-align">
				Hello Engine features a completely implemented Entity Component System, that allows you to create Game Objects (entities) with multiple Components on each of them. This Components give them a determined behavior. Available components are:<br> 
				<b>Transform:</b> To manipulate the GameObject’s position, rotation and scale. Every Game Object has this Component by default, and cannot be removed.<br> 
				<b>Mesh Renderer:</b> Draws a Mesh from the Assets folder using the GameObject’s transform values.<br> 
				<b>Material Component:</b> Adds a texture from the Assets folder as the drawing texture for the Mesh Renderer component inside the same Game Object.<br> 
				<b>Camera Component:</b> Creates a Camera Object that uses the GameObject’s transform values. Can use Orthographic or Perspective view.<br> 
				<b>Script Component:</b> Allows the user to drag any valid .h or .cpp script inside the Assets folder. The script behavior will be called when the Play button is on.<br> 
				All Game Objects share a hierarchical structure that affects their respective Transfrom values. Parenting can be edited through the Hierarchy window, by dragging the Game Object’s nodes.
				</p>
			</div>
		</div>
	</section>
	<section>
		<img class = "image" src="{% link assets/gifs/CFF.gif %}" style="transform:translateY(25%)" alt="" data-position="25% 25%" />
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Custom File Format</h3>
				</header>
				<p class="text-align">
				You can Import files into the project by dragging them in the Hello Engine window. Some files will be imported into a more efficient Custom File Format. The original file is never edited on this process. Our custom file formats include:<br>
				<b>.hmodel:</b> From FBX files, determines the FBX mesh structure.<br> 
				<b>.hmesh:</b> From FBX files, determines a specific mesh’s information (vertices, indices, normals…)<br>
				<b>.dds</b>: From PNG, TGA or JPG, saves image information.<br>
				<b>.helloMeta:</b> Meta data used for the Editor Serialization and Resource Manager systems.<br>
				<b>.HScene:</b> JSON file format that saves all scene necessary data for the Serialization system.
				</p>
			</div>
		</div>
	</section>
		<section>
		<img class = "image" src="{% link assets/gifs/UndoRedo.gif %}" alt="" data-position="25% 25%" />
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Undo/Redo</h3>
				</header>
				<p class="text-align">
				In Hello Engine, you can use Ctrl + Z and Ctrl + Y to Undo / Redo actions from the editor correspondingly. All actions that can be Undone and Redone are saved on a stack. This stack gets reseted when any Scene change occurs, or when the Play button is pressed.
				</p>
			</div>
		</div>
	</section>
	<section>
		<img class = "image" src="{% link assets/gifs/resource.gif %}" style="transform:translateY(25%)"  alt="" data-position="25% 25%" />
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Resource Manager</h3>
				</header>
				<p class="text-align">
				Every loaded Asset has a corresponding Resource that has the relevant asset’s information. This Resource is loaded into memory when needed by any Game Object (Entity) or Component inside the current Scene. The data loaded into the resource is taken from the Custom File Format version of the original Asset, never the original Asset itself. For example, an FBX vertex data will be loaded from our .hmesh file, not from the original FBX.<br> 
				This allows our memory to only load once every needes asset, and share that data into the multiple entities that need it.<br> 
				Also, the Resource Manager creates .metaData files that “watch” every Asset	file, to determine whether this asset changed or has been deleted. When changed, the corresponding Resource gets re-imported. When deleted, the corresponding Resource gets destroyed, and the memory is released.
				</p>
			</div>
		</div>
	</section>
	<section>
		<img class = "image" src="{% link assets/gifs/Serialization.gif %}" alt="" data-position="25% 25%" />
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Serialization System</h3>
				</header>
				<p class="text-align">
				You can save all Entity and Component’s data inside an HScene file using the Serialization System. This Scene files can be then loaded to recover the scene state of the moment of saving. This works using JSON files, that have been renamed to .HScene. 
				</p>
			</div>
		</div>
	</section>
	<section>
		<img class = "image" src="{% link assets/gifs/Scripting.gif %}" style="transform:translateY(25%)" alt="" data-position="center center" />
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Scripting System</h3>
				</header>
				<p class="text-align">
				Hello Engine includes a C++ Scripting system, using Hot Reload and Automatic Compilation. You can use C++ code to create behavior scripts, that can then be added to any Game Object. This behaviors get Started and Updated once the Play button is pressed.<br>
				This works using Visual Studio 2019. 
				</p>
				<ul class="actions">
					<li><a href="generic.html" class="button">More</a></li>
				</ul>
			</div>
		</div>
	</section>
</section>

<!-- Three -->
<section id="three">
	<div class="inner">
		<header class="major">
			<h2>Provided by Hello Games Company</h2>
		</header>
		<p>
		A github organization  created by Xidashuaige & AdriaSeSa which publish college project.</p>
		<ul class="actions">
			<li><a href="https://github.com/HelloGamesCompany" target="_blank" class="button">Hello Company Github</a></li>
		</ul>
	</div>
</section>

</div>

