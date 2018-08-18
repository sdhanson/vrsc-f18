# Unity Lesson Guide

**Curriculum:**
  * What is Unity? Why use it? Best resources for Unity?
  * Unity + Github Set-up and Installation
  * Navigating the Unity Window and Folder Structure
  * Mini-project: Rocket Booster
  * Scene Set-up
  * Game-Objects / Pre-fabs
  * Physics System and Colliders
  * Unity + Github
  * Hotkeys
  * Computer Input
  * Lighting and Rendering
  * Enumerations
  * +++

## Unity Basics
### What is Unity?

“Unity is the ultimate game development platform” and game engine. A game engine is a software development environment designed for people to build video games. Basically, Unity is a tool that provides us a simple(ish) interface to easily create 2D and 3D applications. Unity uses C# and/or JavaScript.

Another popular game engine is Unreal Engine.

### Why use it?

Unity is at the forefront of the XR market. In 2017, 90% of Samsung GearVR and 53% of Oculus Rift games were made using Unity. 

This is because Unity has the most tools and hardware support from XR hardware suppliers, including Oculus and HoloLens. These XR suppliers use Unity as their game engine and provide SDKs (software development kits) for XR development in Unity.

### What are the best Unity resources?
  * Unity User Manual
  * Unity Scripting API
  * Unity Forum
  * Microsoft C# guide
  * Google & the VRSC E-Board!

## Unity + Github Set-up and Installation
### Github Installation / Set-up

Prerequisites:
  - Create a Github account
  - Download Github Desktop

Git is a version control system, or a platform that allows programmers to track, share, and save their code. Github is a service that extends Git and creates a simple interface for developers to use Git. Github is great for XR development because it allows you to share your application with team members and save old versions of the game in case you want to restore an old game version. Github Desktop is a desktop app that is easier to use than the typical Github command line tools, especially for Unity.

**With Github, you can easily clone (aka download) repositories (aka an overarching project folder), make changes to the code, and commit (aka save) your changes to the code base. Check out this guide and get comfortable with Github.**

We will be using Github to provide resources through the vrsc-f18 repository and for version control during development. 

Now, let’s fork the vrsc-f18 repository. A fork is a copy of a repository; you can change the code in the forked version without affecting the original repository.
  - Log into Github
  - Navigate to the vrsc-f18 repo
  - Click “fork” in the upper right corner

That’s it. When you want to use/change the code from the vrsc-f18 repo, be sure to use your forked version.

### Unity Installation / Set-Up
  - Download Unity 2018.2.1 from this page.
  
  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/install.png "Download Specifications")


  Note: The Unity Installer will launch the Unity Download Assistant. Leave the default settings.

That’s it.

## The Unity Window and Folder Structure
### Basic Structure of a Unity Project

Now, we will explore the Unity window/interface and project structure. 

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/new.png "New Project")


Create a new project
  - Open Unity and select “New”
  - Name the project
  - Specify a location to save the project (desktop is fine)
  - Keep the 3D template
  - Create!

Unity will open to the default window with a blank scene. The default window has a few main sections: 
1. **Project / Console**
    
    a. **Project**: All the files in your project (like file explorer). You can drag and drop files into this area to add files to your project. 
    
    b. **Console**: The window where you will see Debug messages, errors, etc when you run your project.

2. **Inspector**: A detailed view of a selected component in the scene.
3. **Hierarchy**: All the game objects in the scene and their relationships.
4. **Scene / Game**:

    a. **Scene view**: Shows the currently open scene
    
    b. **Game view**: Shows what the game looks like when you hit play. 
    *Activates when you enter play mode (aka hit play). Play mode allows you to test your game and make changes. However, when you make changes in play mode, nothing is saved, so determine which tweaks you like, end play mode, and then redo the tweaks to make them last. You can give play mode a different color by going to Edit | Preferences | Colors | Playmode tint*
    
      ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/tint.png "Playmode Tint")

    
    c. **Toolbar**: Pan, Move, Rotate, Scale, Rect, Catch-All. Pivot, local. Play, Pause, Advance. We will get into each of these in more detail later on.

You can move around each section for a workflow you like. This is my default workflow:

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/workflow.png "Download Specifications")


Unity has opened us up to a default, untitled scene. Here is a great description of scenes from the Microsoft Unity guide:

“Everything that runs in your game exists in a scene. When you package your game for a platform, the resulting game is a collection of one or more scenes, plus any platform-­dependent code you add. You can have as many scenes as you want in a project. A scene can be thought of as a level in a game, though you can have multiple levels in one scene file by just moving the player/camera to different points in the scene. When you download third-party packages or even sample games from the asset store, you typically must look for the scene files in your project to open. A scene file is a single file that contains all sorts of metadata about the resources used in the project for the current scene and its properties. It’s important to save a scene often by pressing Ctrl+S during development, just as with any other tool. 

Typically, Unity opens the last scene you’ve been working on, although sometimes when Unity opens a project it creates a new empty scene and you have to go find the scene in your project explorer. This can be pretty confusing for new users, but it’s important to remember if you happen to open up your last project and wonder where all your work went! Relax, you’ll find the work in a scene file you saved in your project.

In a scene, you can’t see anything without a camera and you can’t hear anything without an Audio Listener component attached to some GameObject. Notice, however, that in any new scene, Unity always creates a camera that has an Audio Listener component already on it.”

And, here’s a great description of Unity GameObjects from the Microsoft guide:

“Virtually everything in your scene is a GameObject. Think of System.Object in the .NET Framework. Almost all types derive from it. The same concept goes for GameObject. It’s the base class for all objects in your Unity scene. All of the objects shown below derive from a GameObject. 

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/graph.jpg "GameObject Graph")


A GameObject is pretty simple as it pertains to the Inspector window. You can see in the figure below an empty GameObject that was added to a scene; note its properties in the Inspector. GameObjects by default have no visual properties except the widget Unity shows when you highlight the object. At this point, it’s simply a fairly empty object.

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/gameobject.png "GameObject in Hierarchy")

 
A GameObject has a Name, a Tag, a Layer and the Transform (probably the most important property of all).

The Transform property is simply the position, rotation and scale of any GameObject. Unity uses the left-hand coordinate system, in which you think of the coordinates of your computer screen as X (horizontal), Y (vertical) and Z (depth, that is, coming in or going out of the screen).

### Components
You add functionality to GameObjects by adding Components. Everything you add is a Component and they all show up in the Inspector window. There are MeshRender and SpriteRender Components; Components for audio and camera functionality; physics-related Components (colliders and rigidbodies), particle systems, path-finding systems, third-party custom Components, and more. You use a script Component to assign code to an object. Components are what bring your GameObjects to life by adding functionality. You can also add scripts to GameObjects, which can define certain functionality for the GameObject.”
Here’s an example of the Unity window with an open scene from the Sharp Shooter Tutorial:

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/sharpshooter.png "Sharp Shooter")


In the Hierarchy, we see all of the GameObjects for the Level 1 Scene. The Inspector shows us the details for the selected object, the main camera. In the Project tab, we see all of the imported assets for the project, including audio, textures, scripts, etc--everything we need to create this scene/level.
While we only see the Assets folder in the Project window, the Unity project structure also includes Library, ProjectSettings, and Temp folders. This can be seen in the folder where you saved your Unity Project. For example, my Intro project is like this:

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/finder.png "Finder")


The Library folder holds metadata for assets. The ProjectSettings folder contains specific configuration settings for your project. The Temp folder is only present while the Unity Project is open; it contains temp files Unity needs to build your project as you work on it.

While the project structure is not that important to understand for development, it will be helpful to know the basics when we use Github with Unity.

## Mini-Project: Rocket Booster

Let’s dive into Unity by creating a simple 3D rocket game. At points, I will point out side notes that give interesting information, but are not crucial for a beginner’s understanding.

### Part 1
Main Objectives:
  * Basic Project / Scene Set-up
  * Lighting
  * GameObjects
  * Meshes / Materials
  * Individual Task: Creating a Rocket Ship
    * Primitives
    * Placeholder Art
    * Prefabs
    * Grouping

#### Creating the Project with a Github repository
First, we will create a new Unity project and set it up with a Github repo.
  - Create a new repository on github.
  - Clone the repository onto the Desktop.

Now, launch Unity.
  - Select New.
  - For the Location field, find the GitHub repository you just made. I.E. I would select /Users/sarahanson/Documents/Github/vrsc-unity-test as the location for my project.
  - You can name your project whatever you like and keep it as Unity 3D.

#### Individual Task
  - Create a “Scenes” folder in the **Assets** folder
  - Save the open, untitled scene as “Level 1”

Now, head back over to Github Desktop and look at your repository for this project. There are a bunch of new files! Create a commit message and **publish the repository**.

These are the basic steps for starting a game. It is a good idea to have different folders in the **Assets** folder for **Scenes**, **Scripts**, **Materials**, **Prefabs**, etc.

### Default Scene (Lighting)
If you take a look at the default GameObjects in your scene, you will see a **Main Camera** (with an Audio Listener) and **Directional Light**! We already covered the purpose of the main camera (seeing) and the audio listener (hearing). 

#### Lighting
The default directional light is an ambient light, meaning it illuminates all surfaces in the scene and doesn’t come from any specific source object. This means, you can move around the default light and it won’t change the scene lighting. However, rotating the directional light will change the scene lighting.

Side note: Other types of lighting include, point lights (think of lamps or light bulbs), spotlights (like a point light but stops at a certain range), emissive materials (like a neon sign), and area lights (like directional light for a small area). Read more.

### Creating Our Game: The First GameObject
Our game is a rocket game. For this game we will need an environment, including a ground, a rocket, obstacles, etc.

Let’s start by creating the ground!
  - Instantiate a **cube GameObject**. Rename this to something like “Terrain”.
  - Make sure to center the cube by setting the Position X Y Z to 0 0 0 or going to the **Transform > Settings wheel > Reset** in the cube’s Inspector.
  - The cube is too small to be our large ground, so let’s make the cube a bit larger by altering the **scale** to 100 30 100. Then, make the ground’s Y align with the origin by setting it down by -15. 

You should now have a terrain like below:

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/terrain.png "Terrain")

Side Note: As we transform GameObjects (i.e. rotate, change the position, scale, etc) you can use the Inspector to make these changes, Unity hotkeys, or the Toolbar:

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/toolbar.png "Toolbar")

Select, transform, rotate, scale, GUI, all

Side note 2: Unity has a built in Terrain system that allows you to create really cool landscapes. If this sounds interesting to you, check it out. Otherwise, a plane is just fine for mimicking the ground.

### Meshes / Materials
The key things to note about our new ground are the **Mesh Collider**, **Mesh Renderer**, and **Mesh Filter** components. 

**Meshes** are like wireframes of an object. They give 3D objects their shape. The **Mesh Filter** component specifies the shape as one of Unity’s built in meshes, a cube. The **Box Collider** component is used by the Unity Physics Engine to specify the boundaries of the object and help with collisions and such. The **Mesh Renderer** component actually renders the object (makes it visible). 

Also note, the terrain has a “default shader” attached to it.

   ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/shader.png "Default Shader")


This **shader** component is empty--it has no values set and thus makes the terrain look white--and can be tweaked to create any type of look for the terrain. We could texture the terrain (i.e. give it a rocky look), tweak how it interacts with light, etc, but for now, we will simply change the color of the terrain.

In order to change the color of the terrain, we will create a new material:
  - Go to **Assets > Create > Material**. 
  - You will see a **New Material** asset is created in your **Assets** folder. Change the **albedo** on the asset to a nice ground-ish color.
  - Rename the material to something like “ground” 
  - Drag the asset onto the terrain **GameObject** 

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/material.png "Terrain Material")


Each material comes with a standard shader; when you add a new material to your GameObject, this shader will replace the old default shader on your GameObject. You can fiddle around with the other settings on the shader, but, for now, know this is the easiest way to give colors and textures to your GameObjects.

Great! So the ground is set.

### Individual Task: Creating a Rocket Ship
I am going to give you some background information on primitives, hierarchies, prefabs, and grouping objects. Then, you will have some time to create your own rocket!

### Primitives
We will be using primitives (Unity’s built in cube, sphere, place, etc) to model different objects in our game. These primitives can later be replaced with actual models, or, if they look cool enough, they can be kept in the game down the line.

### Hierarchy of Placeholder Art
When making a placeholder primitive art form, it is important to group the individual primitives (aka a cube representing a rocket body, a capsule representing the rocket nose, etc) that compose the overall art form (aka a rocket ship) under an empty game object and name everything appropriately, like so: 

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/hierarchy.png "Rocket in Hierarchy")


This is a nice example of Unity’s hierarchy. We can make a GameObject a child of a parent GameObject. Child objects inherit the **position** and **transform** of the parent object, so when the child’s transform is at 0 0 0, it is at the parent object’s position.

In this example, “Pretty Rocket Ship” is an empty GameObject, while the child Rocket Body is a cube. The children, “Starboard Booster” and “Port Booster”, are empty GameObjects with sphere “Tail” components nested underneath. 

### Prefabs
In this example the GameObjects are blue! This means that they are **prefabs**. A **prefab** is a template for an object. So if you make a cube, scale it, rotate it, give it a material, and you want to use that exact set up again you can 1. duplicate the cube OR 2. create a prefab. To create a prefab, you drag the cube from the hierarchy to the assets folder. Then, you can use the template by dragging the prefab from the assets folder to the hierarchy. * You can make overall changes to prefabs that apply to every single prefab, which we will go into later *

Side note: **Meshes should be kept away from the top level**. Aka each individual component (tail, rocket body) should have a mesh, but empty parent objects should not.


### Grouping
It is important to note that you can “snap” GameObjects into place with control shift / command shift (pc / mac). This helps the physics engine calculate the center of gravity as the center of the group of objects, not just one object.

### Your Turn
  - Make a rocket ship using primitives.
  - Make your rocket ship a prefab (hint: drag your complete rocket ship into Assets > Prefab folder)
  - Make a platform for the rocket ship to stand on.
  - Add some materials to make things pretty!

Don’t forget to use the toolbar or Inspector to reset your GameObjects to the origin, scale the objects, and move them however you want.

### Example Rocket (from yours truly):

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/rocket.png "Rocket")

Alright, so now we all have a rocket ship! Yay!

### Next Steps

If we press play and enter game mode, nothing happens! This game is really boring right now!

We want to let the user control the rocket ship and fly around the landscape. In order to add this interaction, we will need to learn about the Unity physics system & C# scripting.


### Part 2
  * Main Objectives:
  * Physics system
  * C# Scripting
  * Colliders
  * Tags
  * Levels / Scene Management
  * Coroutines and Enumerations
  * Particle Effects

### Physics System and Colliders
Here is a great description of a physics system from the Unity Manual:
“To have convincing physical behaviour, an object in a game must accelerate correctly and be affected by collisions, gravity and other forces. Unity’s built-in physics engines provide components that handle the physical simulation for you. With just a few parameter settings, you can create objects that behave passively in a realistic way (ie, they will be moved by collisions and falls but will not start moving by themselves). By controlling the physics from scripts, you can give an object the dynamics of a vehicle, a machine, or even a piece of fabric.”

Key words:
  1. Collisions: A collision occurs when the physics engine detects that the colliders of two GameObjects make contact or overlap, when at least one has a rigidbody component and is in motion.
  2. Component: A functional part of a GameObject
  3. Scripts: A piece of code that allows you to create your own Components, trigger game events, modify Component properties over time and respond to user input in any way you like

The key components in the Unity physics system are:
  1. **Rigidbody**: A **Rigidbody** is the main **component** that enables physical behaviour for a **GameObject**. With a Rigidbody attached, the object will immediately respond to gravity. If one or more **Collider** components are also added, the **GameObject** is moved by incoming **collisions**
  2. **Collider**: **Collider** **components** define the shape of an object for the purposes of physical **collisions**. A collider, which is invisible, need not be the exact same shape as the object’s **mesh** and in fact, a rough approximation is often more efficient and indistinguishable in gameplay.

We will see these in detail and in our own game, so don’t worry if the physics system is confusing at the moment.

### Adding Physics to our Game
We want to make the rocket move! To do this, we will enable physics behavior on our rocket. Then, we can move the rocket by adding forces and have it respond to gravity like an actual rocket. As we read above, the **Rigidbody** component enables physics behavior for a GameObject. 

  - Add a **rigidbody** to the top level of the rocket ship.
    - Note: The rocket ship has been given a **mass**, **drag** (how syrupy the air is), and **angular drag**.
    - Testing: To test the physics, pull your rocket ship off of the ground/platform and press play. The rocket should fall to the ground. If it falls through the ground or platform, add a **collider** to the ground or platform.
    - Note: The collider tells Unity that something is there and we can’t go through it. In fact, we don’t need a mesh (external look) for things to collide. You could make an invisible box with a box collider and it will collide with the rocket ship.
  - Add a **script** “Rocket” to the top level of the rocket ship. 
    - We will use this script to control the motion of the rocket. 

### Scripting
*Important to get your naming right*
Open the Rocket script by double clicking on it. The script should open in MonoDevelop--Unity’s built in editor--unless you configured a different default editor.
The Rocket script has a default structure. Read more about it in the Unity manual.

Quick overview of scripting: The default script is derived from the base class, MonoBehaviour, which makes sure the script will run in the game loop and gives us added built in functionality. Unity provides predetermined methods, including:
1. Start( ): gets called once right before the script gets the first update
2. Update( ): fired every frame--depends on framerate; used for graphics
3. FixedUpdate( ): fired every 0.02 seconds--independent of framerate; used for the physics engine
4. OnDestroy( ): fired right before the GameObject the script is attached to gets destroyed
5. OnCollisionEnter( ): fired when the collider or rigidbody of the GameObject the script is attached to collides with another collider or rigidbody

### Rocket Script
The first motion we are going to add to our rocket is the ability to thrust upward (space bar) and rotate left (A) and right (D). 

[Rocket Script](https://gist.github.com/sdhanson/12c354bc3ba1147dd705a4e22a16c8ce.js)

We will walk through the code above, which is explained in the code comments.

### Your Turn
Play the game! If your rocket ship doesn’t move, try and lower the mass of the ship until it moves at a speed you like.

Our rocket is somewhat unstable, so freeze the position in the z direction and the rotation in the x and y direction on the rocket’s RigidBody.

   ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/constraints.png "Rotation constraints")

### Controlling the Rocket Speed
Now, it would be really cool if we could control the speed of our thrust and rotation. Let’s add some variables to do just that.

[Rocket Script](https://gist.github.com/sdhanson/b6640b5d33066687524f61cdcb40dd38.js)

We will walk through the code above, which is explained in the code comments.

### Your Turn
  - Change the **mass** of the RigidBody so it is back at 1
  - Change the **rcsThrust** and **shipThrust** variables in the Inspector so that your rocket ship moves like it did before.

Side Note: If you change a value while playing the game, your changes are lost when you stop playing!

### Example: My Rocket Ship Values

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/values.png "Rocket Values")
  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/values2.png "Rocket Values")


### Collisions
#### Your Turn
Create a field of obstacles for your rocket to maneuver around. 
  - Create one **primitive obstacle**.
  - Name it “Obstacle” or something of that sort
  - Add a **material**.
  - **Prefab** the obstacle.
  - Use the prefab to create a set up of different obstacles
  - Create a **second platform**, the “landing platform” at the end of the series of obstacles, give it a material, and create a new prefab “landing platform”
  - Move the camera around so you get a good view of the game in the Game view, like below:

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/level1.png "Level 1")


#### Tags
From the Unity Manual: A **tag** is a reference word you can attach to one or more GameObjects. It is used mostly for scripting purposes as they are useful triggers for Colliders in scripts; they need to work out whether the player is interacting with an enemy, a prop, or a collectable, for example.

We will use tags to tell us if the rocket has collided with a good object (the start platform), has finished the level (the landing pad), or should die (anything else).

To create a tag for the friendly starting platform:
  - Go to the starting platform GameObject
  - Go to **Tag > Add Tag > +** 
  - Create a new tag named “Friendly”
  - Go back to the platform **GameObject > Tag > Friendly**
  
#### Your Turn
Tag the landing pad as “Finish” 

### Using Tags + Collisions in a Script
To get the basic feel of how to use **tags + collisions** in a script, we will simply add a function to our script that prints out “friendly” when we collide with a friendly tagged object, “finish” when we collide with a finish tagged object, and “dead” when we collide with anything else.

[Rocket Script](https://gist.github.com/sdhanson/4fde37c5d196b32ee3dd7e671390f741.js)

We will walk through the code above, which is explained in the code comments.

Play the game and make sure the console prints out the correct statement for each collision.

### Levels
Now, we will set up the skeleton of the second level and the game flow. From there, you can customize your levels as much as you want on your own and make some really cool rocket games!!

First, let’s duplicate our Level 1 scene in the **Assets > Scenes** folder. Click on the Level 1 scene and go to **Edit > Duplicate**. Rename the duplicated scene to “Level 2.” 

Open the duplicated scene. It should look the exact same as the Level 1 Scene. Change something around so you don’t get confused with the scenes--maybe give the ground a new color, the obstacles a new material, or move around the obstacles.

It is important that we can clearly tell which scene we are on just be looking.

### Scene Management
Now, let’s implement a game flow and link the two levels. Our game flow will be this: You start on Level 1. If you die (hit an untagged surface) on Level 1 or Level 2, you go back to Level 1. If you are on Level 1 and you make it to the landing pad, you go to Level 2. If you are on Level 2 and you make it to the landing pad, you ….. we’ll leave this choice up to you!! Maybe you start back on Level 1, maybe you make a Level 3, maybe you make a Win Screen. For now, we’ll just start back on Level 2, but feel free to change this up!

To switch scenes in Unity, we can use the Unity SceneManager which allows us to manage at during run time. The SceneManager gives us easy access to scenes that are in our build through their index. This means, we have to add Level 1 and Level 2 to our build scenes. 

With Level 1 open go to **File > Build Settings > Add open scenes**. 

  ![alt text](https://github.com/sdhanson/vrsc-f18/blob/master/lesson-1/images/build.png "Build Settings")


Now, the scenes we want in our game are in the **Scenes in Build** and are checkmarked with an index next to them. We will later access these scenes using their indices in our Rocket script.

Also note, the **build settings** is where you specify information about what device you want to build your platform on. This is important for virtual reality because we will have to install some APKs that give us access to certain headsets.

### Scenes + Scripting
Let’s implement the actual **game flow**. Earlier, we decided to print “friendly,” “finish,” or “dead” based on the tags on GameObjects the rocket collides with. Now, let’s add functionality to actually transition the scene with the flow we described above.

[Rocket Script](https://gist.github.com/sdhanson/c2cc706b7df4b067a4c5afb55b980423.js)

We will walk through the code above, which is explained in the code comments.

### Your Turn
Play the game! Make sure when you hit an untagged obstacle you go back to Level 1 and if you complete a level you go back to Level 2.

### Lighting Bug Fix
Yay! Your scene loads correctly… but the lighting is way off! This is a built in bug in Unity. To get our scenes to load with the lighting we want, we must:
  - Go to **Window > Lighting > Settings**
  - Untick **Auto Generate**
  - Click **Generate Lighting**

Unity was trying to make the lighting for your scene at runtime...and failing. Now, your lighting for each level should be saved in an assets folder that Unity will load along with the level.

### Coroutines
When you play your game, you should see that when a scene transition is triggered, the next scene loads immediately. This abrupt change is not the best game experience. We will now use coroutines to delay the scene transition by 1 second.

Unity functions act sequentially—Unity does not move to the next function until another function ends, basically stopping all other functionality. A **coroutine** is a function that has the ability to pause execution and return control to Unity and then continue where it left off the following frame.

**FixedUpdate** is called every 0.02 seconds, so if we delay a function by 1 second in FixedUpdate, the function will never actually execute! However, we can **start** a coroutine in FixedUpdate, and then let the coroutine function run separately from FixedUpdate.

Coroutines have unusual syntax. Remember—they are functions, and they are declared like so:

IEnumerator SomeCoroutine(float delay = 0.0f) {
	if(delay != 0f) {
		yield return new WaitForSeconds(delay)
	}
	// rest of the function here
}

They are called from FixedUpdate (or any other function) like so:

StartCoroutine(SomeCoroutine(1f));

Let’s see this in practice in our code.


### Particle Systems
Finally, we will add some fun **particle effects** to our game. Unity provides a built in particle system that allows us to emit different “particles” from GameObjects. These “particles” are 2D default objects that we can customize with speed, color, texture, etc. They are emitted in 3D but they are 2D objects that are always oriented towards the canvas, so they always look like squares. 

Our game will utilize three particles systems for different states of our game: a particles system when we are thrusting, a particles system when we collide with an obstacle and die, and a particle system for when we win a level! We will attach particle system GameObjects to our Rocket and **trigger** these particle systems from code.

Before we dive into how to create and use a particle system, we will take a look at enumerations.

### Enumerations
**Enumerations (or enums)** are custom types that we create in our script. They are a collection of words that are usually used to indicate different states of our game.
For example, we might have an enumeration, like:

	enum State { Alive, Dead, Zombie };
	State state = State.Alive;

Then, we will switch our game functions depending on if we are alive, dead, or zombie, like so:

	switch(state) {

		case(state == State.Dead):
			print(“You lost!!!”);
			break;
		case(state == State.Zombie):
			print(“Attack those people!”);
			break;
		default:
			print(“Keep going!”);
			break;

	}

In our game we will have three states, Alive, Dying, and Waiting, and these states will help us determine what movements are available to the player and what particle effects should be playing.

### Create and Use a Particle System
We have provided a unity package of the particle system you should download right here. 
  - Download this package
  - Move the package to your **Assets** folder
  - Open the package in Unity. You will now have three particle systems prefabs. 
  - Feel free to move them to your **Prefabs** folder. 
  - Attach all three particle systems to the rocket ship. 


Take a look at one of the particle systems. Note the particle systems are **GameObjects**, and they are child GameObjects of the Rocket--the Rocket itself is not a particle system. In order to make a particle system GameObject, simply **vattach a particle system component to an empty GameObject**. In the particle system component, you can see all sorts of specializations. The most important thing to note is that play on awake has been disabled. This means, we must trigger the particle system to play in our code, which we will do below.


### What’s Next?
We did not cover everything in Unity, but we did hit a lot of the basics. This lesson should serve as a guide for development as you get started, and feel free to reference it from here on out. However, it is our hope that you go forth with your new Unity knowledge, feel confident in your abilities, and try out some really cool things. 

We’ve given you the basic tools to get started, now make some cool games!

Some interesting things we didn’t cover are:
  * Animation
  * Audio
  * Raycasters
  * Graphics / Shaders
  * UI

These are all very important to a VR game/application, but we did not have time to cover them. Don’t worry, these basics are really important, too.

The Unity Manual, Unity Forum, YouTube, and the VRSC Unity Team are the best resources to learn more!




