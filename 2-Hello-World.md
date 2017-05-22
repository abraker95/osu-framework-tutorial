# Part 1

Anything derived from `Game` needs two methods: `load()` and `Update()`. `load()` is used for creating the objects and specifiying their structure. `Update()` runs those objects' bahaviors. The text object we are going to display is called `SpriteText` and it will go into the `load` method. `SpriteText` has several properties, but the ones we are going to be setting in this part are the text contents, position of the text, and colour of the text. When creating an object for the app to use, we need to add it to the environment using the `Add` method. The code is as follows:

	using OpenTK;				// For Vector2
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


# WIP

