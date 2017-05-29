# Part 1

Anything derived from `Game` needs two methods: `load()` and `Update()`. `load()` is used for creating the objects and specifiying their structure. `Update()` runs those objects' bahaviors. The text object we are going to display is called `SpriteText` and it will go into the `load` method. `SpriteText` has several properties, but the ones we are going to be setting in this part are the text contents, position of the text, and colour of the text. When creating an object for the app to use, we need to add it to the environment using the `Add` method. The code is as follows:

	using OpenTK;				// For Vector2
	using OpenTK.Graphics;    		// For Color4
	using osu.Framework;
    using osu.Framework.Allocation;		// For BackgroundDependencyLoader
    using osu.Framework.Graphics.Sprites; 	// For SpriteText

    namespace HelloWorld
    {
        class HelloWorld : Game
        {
            [BackgroundDependencyLoader]
            private void load()
            {
	            // Add a new SpriteText object
                Add(new SpriteText
                {
                    Text = @"Hello World!",
                    Position = new Vector2(100, 100)            // make it appear 100 pixels from left and 100 pixels from top of the window.
                    Colour = new Color4(1.0f, 0.0f, 0.0f, 1.0f) // make the text red
                });
            }

            protected override void Update()
            {
                base.Update();
            }
        }
    }


The `Add` method adds objects that are derived from the `Drawable` base class. `SpriteText` is one type derived from `Drawable`. Another type of object is derived from `Drawable` is `Box`. When a `Box` object is added to the environemnt, a rectangle is displayed. In this example we will set the `Size`, `Position`, and `Colour` properties of the `Box` object. The following code can be added into the `load` method:
	
	Add(new Box
	{
		Size = new Vector2(100, 50),			// set the rectangle to be 100x50
                Position = new Vector2(300, 100),		// set the rectangle to be positioned at (300,100) at its top-left corner
                Colour = new Color4(1.0f, 0.0f, 1.0f, 1.0f)	// set the rectangle to be magenta
	});

# WIP

