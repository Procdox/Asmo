## Programming Languages for Art Development

A short* guide to programming languages used in popular game engines
1) [Unity](#Unity)
2) [Unreal](#Unreal)
3) [Toolchains](#Toolchains)

# Unity
Programming is primarily done in (in order of artist to engineering focused)
1) [Visual Scripting](#1-Visual-Scripting)
2) [UnityScript](#2-UnityScript)
3) [JavaScript / Python / Lua](#3-JavaScript--Python--Lua)
4) [C#](#4-C)
5) [C / C++ / Rust](#5-C--C--Rust)

Being familiar with 1 and 4 is almost certainly going to be a must have for any Unity focused technical role.
## 1) Visual Scripting
Unity nowadays has an out of the box visual scripting system similar to (but not as feature rich as) Blueprints in unreal. This is designed for ease of use and rapid prototyping of small scale systems. Comes at a cost to performance. Prototypes will almost always be migrated to C# code when prototyping is finished. It also can call into custom C# nodes to allow access to project specific code. A familiarity with this newer system is not a bad idea, but it is probably not where most of your work would be done.
https://learn.unity.com/project/introduction-to-visual-scripting

## 2) UnityScript
Unity supported a weird hybrid of C# and Javascript, I don't believe it's used (or supported) anymore. But it was meant to be an easier unity-specific syntax to full powered C#. Probably not applicable anymore.

## 3) JavaScript / Python / Lua
There are addons to support development in Unity with other popular languages, these -might- be relevant with regards to game/engine development itself on certain projects.
https://pleasenophp.github.io/posts/using-real-javascript-with-unity.html

## 4) C#
The bread and butter of development in Unity. Not my personal play ground but still very powerful. Full of quirks and weirdness but with some features that make it amazing to work with as both a developer and a modder. C# code ships AS c# code, it is not compiled like C/C++/Rust, meaning you can fully decompile a Unity game and get back the exact code that makes the game tick. This makes modding games and exploring the guts of games a great way to learn C#. The best place to start imo, and if you want to goof around and try your hand at modding a game I'd be down to help / work with you.
https://learn.unity.com/course/beginner-scripting
https://github.com/icsharpcode/ILSpy
https://github.com/BepInEx/BepInEx

## 5) C / C++ / Rust
Development in these languages is not directly supported in Unity, however they can compile to "libraries" which act as bits of code that the main game code can use to execute pre-compiled code, giving your C# code access to functionality not supported by Unity out of the box. It also can be used by engineers to create code that is faster than it would be in C# for time sensitive portions of your code (physics simulations and such.)
I would not recommend starting here for unity...<br>
As for Unreal...

# Unreal
programming is primarily done in (in order of artist to engineering focused)
 1) [Blueprints (Visual Scripting)](#1-Blueprints)
 2) [C++](#2-C)

Yeah that's pretty much it... 

## 1) Blueprints
The non-engineer's magic bullet for Unreal, because when the only tools you have are this or C++... You should probably stick with this if you don't well know what you are doing. That isn't to say that blueprints aren't powerful as hell. Top level logic for everything is generally done in these. Game Logic, AI, Animation... These of course aren't as fast as C++, and they are an absolute mess to maintain if they hit a certain size. The general rule is that high level logic stays in Blueprint land, but calculations are done in...

## 2) C++
The entire engine of Unreal is open-source and written in C++, making it WILDLY flexible/extendable. It also makes use of "a custom pre-compiler for automated generation of linking code from Unreal specific attributes". This just means you can have a single line of code that says "I want this value to be editable from the Unreal Editor" or "I want this function to be callable from blueprints" and the compiler will do the leg work for you. This makes C++ very easy* to extend blueprints or any in-engine system with further functionality. Of course with great power comes complications. That is to say that even the smallest of tasks will require quite a thorough understanding of both C++ and Unreal Engine. God I love it. God I hate it. Get used to seeing that Unreal Crash Reporter dialog, even in the editor.

# Toolchains
For everything that isn't in engine, you have toolchains. Going over an exhaustive list of every possible language a team could use is akin to going over every language invented. Most likely though:
1) [Python](#1-Python)
2) [Shell languages e.g. Bash/Powershell](#2-Shell-Languages)
3) [Javascript](#3-Javascript)

## 1) Python
It's easy, it's slow, it'll do anything you want and it won't take a week to debug.

## 2) Shell Languages
OS dependent, easy and slow, but also great for automating simple shit. Not quite as powerful as python, but also a lot simpler for some things like executing commands or moving around files. 

I use both Python and shell languages every day to automate simple shit. Tired of typing in the same 3 commands? Write a python or shell script and now it's only one command (and you don't have to type in all the baked in argumenets) Inevitably given enough time, any of these tools will have features tacked onto them until using them is more complex than what they are designed to automate. So you make another script to automate your last script.

## 3) Javascript
Internal web tooling, data visualizers, mock ups... I hate everything about it... For my own purposes Javascript with HTML5 is -fine- for anything that requires more visualization than is easy to do in Python. 