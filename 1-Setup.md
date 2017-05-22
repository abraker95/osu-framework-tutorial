# Preface

This tutorial assumes that you have decent knownledge of Visual Studio and C#. After forking the osu-framework, run the sample game project provided. If there are issues getting that to work, head to #osu-client in the the osu!dev discord server [here](https://discord.gg/ppy) and ask about the issue.

# Setting up a new project

Create a new project in under the osu-framework solution named HelloWorld. Your project file structure should look like this 

![old file structure](http://i.imgur.com/Y2ulFTM.png)

First let's take care of the references. We are not going to be using most of the System.* references, so we can delete those. Do keep the one the displays System on its own. Next we are going to add references by right clicking "References" -> "Add Reference..." . The ones we need are:

	mscorlib
	OpenTK
	osu.Framework
	osu.Framework.Desktop

mscorlib is self included in some cases, so we don't need to add it. In case you do, it can be found in the assemblies list. The osu.Framework files can be found in the Projects section. The OpenTK reference needs to be aquired as a NuGet package. There are several variations of OpenTK, but the one we need is the forked version for this framework called ppy.OpenTK. After adding the needed references, the structure should look something like this, with ppy.OpenTK adding some additional references.

![new file structure](http://i.imgur.com/dUgMKIz.png)

# Making a runnable app

After adding the references, you can now start writing code. We will have two sources: Program.cs and HelloWorld.cs. Program.cs serves as an entry point for our program while HelloWorld.cs is the contents of the program. 

Program.cs:

    using System;
    using osu.Framework.Desktop;
    using osu.Framework.Platform;
    using osu.Framework;

	namespace SampleGame
	{
	    public static class Program
		{
	
			[STAThread]
			public static void Main()
			{
			    using (Game game = new HelloWorld())
			    using (GameHost host = Host.GetSuitableHost(@"Hello World!"))
			    {
			        host.Run(game);
			    }
	        }
 	    }
	}

HelloWorld.cs:

    using osu.Framework;

	namespace HelloWorld
	{		    
		class HelloWorld : Game
		{

		}
	}

If all goes well, you will see a black screen with a Runtime notification on bottom left corner. Congradulations! You have the framework set up and are ready to start playing around with it. Next we will make the classic "Hello World" app.
