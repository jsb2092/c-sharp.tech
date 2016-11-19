---
title: "A look at Visual Studio Code"
published: true
categories:
  - Editors
tags:
  - editor
  - c#
  - cross platform
date: 2016-11-17T15:45:00-04:00
---

Many moons ago, Vi was created.  Many years after, Vim was created.  Vi/Vim was (and on many systems still is) my go to editor.  It is installed on pretty much every system ever; if there is a terminal, then there is Vi.  It is highly configurable, and config files could be easily copied to other machines and they would just work.  Let's not forget about Vi keybindings - a lifetime to learn, impossible to forget.

It was therefore, 18 months ago, when Microsoft released Visual Studio Code, I was both excited and confused.  I was excited because I thought that cross platform Visual Studio was a thing.  Turns out, I was wrong (more on that in another post).  I was disappointed because I have been through MANY editors, and frankly, I didn't want to have to look at another one, but 18 months have passed, here we are, and it's a good thing.

In the past year and a half, Visual Studio Code has grown into my favorite go to editor, for almost anything.  Why, you may be asking?  Didn't I just say how awesome Vi/Vim was?  Yes, I did, and Vi/Vim is still my go to editor on platforms where I can't get access to code, or don't have a GUI (ssh'ing into a router, for example), but for writing code, that doesn't require a full fledged IDE, Visual Studio Code is amazing.

I am actually writing this in Code at the moment, for a variety of reasons.  The first is the preview {% picture code-preview.PNG data-downloadable="true" alt="Preview"%}
feature available to documents that can be rendered, such as HTML and Markdown.  Text based Vi can't do this (though that should be obvious), and while I'm not trying to start a Visual Studio Code vs. Vi debate, it is important to point out the reasons I have selected to use Visual Studio Code as my day-to-day editor.


The second reason I am in love is the support for extensions.  Sublime calls these plugins, and they do essentially the same thing.  The big difference here is that Sublime uses Python based extensions, while Code uses Typescript based extensions.  I'm personally a fan of the Python model, but that is mostly because I am very comfortable in Python.  The Typescript/Javascript model is a bit foreign to me, but clearly it works well, as the list of extensions is ever growing.  One day I will write an extension for this beautiful editor.

While Code wasn't what I expected when it was first released, the support for cross platform development is third of my list of reasons that I love this editor.  With recent additions, and the release of [.net core](https://www.microsoft.com/net/core#windowsvs2015), it is very possible (and relatively easy) to write C# code on Linux, Mac or Windows.  The fact that Visual Studio Code can be used as a debugger, and the ability to step through code make it significantly better/easier than any other editor to write cross platform C# code.  I am scheduled to teach a class on Parallel and Distributed Computing, and I am planning on doing that in in C#, and with Code, I should get far fewer complaints of "I can't do this project because I'm using Linux."

Fourth on my list of reasons is the support for other language.  I do love [Visual Studio](https://www.visualstudio.com/) and [PyCharm](https://www.jetbrains.com/pycharm/) for developing complex systems in C# and Python, respectively, but neither of those platforms handle the myriad of languages I use on a daily basis, from HTML, Markdown, Ruby, Python, C#, Java, Javascript, C++, Latex, and more.  The fact that there is support for most of these languages, and many of them have a debugger means that if I want to write a simple program, whether it be for class, or some code I want to post to github, this is a fast, easy to use editor.

Since I'm not intending this to be a top-ten list, I figured I should tell you some of the things I am not impressed with.  The first is a pro and a con - the settings.  It is so configurable that you can make the editor pretty much anything you want.  The downside to this is that trying to figure out how to change, what many editors would consider simple, settings, is sometimes frustrating.   

The second thing that drives me a bit batty is the git integration.  It should work flawlessly, and in many cases, it does.