# Step 2: Sprites and Objects

Before we can write any code, we need to make some art for the player, and the shapes we're gonna shoot.

## Creating Sprites

Right-click on the "sprites" folder in the Asset Browser on the left side of the screen.
Then select "Create > Sprite"

![Creating a Sprite](img/step2-01.png)
/// caption
Creating a sprite
///

Now you should have a new Sprite!

![Sprite in Workspace](img/step2-02.png)
/// caption
The Sprite Editor
///

![Sprite in Asset Browser](img/step2-03.png)
/// caption
The sprite in the Asset Browser
///

## Renaming Sprites

Let's name our sprite "spr_player". You can rename your sprite by clicking the box in the top-left of it's window,
or by double-clicking on the item in the Asset Browser

!!! tip

    It is recommended to follow :simple-gamemaker: GameMaker Studio's naming guidelines.
    Sprite names should *always* begin with "spr_" to signify that it is a sprite.
    This becomes extremely handy when using auto-complete while writing code, as all the sprites will be grouped together.

![Renamed Sprite](img/step2-04.png)
/// caption
Our renamed sprite
///

## Resizing Sprites

Before we jump into making the sprite, lets quickly resize our canvas size.
64 x 64 pixels is a bit big for our use case today.

Click on the :material-arrow-expand-all: icon on the left-hand side of the sprite editor, and adjust the values to 32 x 32 pixels.

![The Resize Button](img/step2-05.png)
/// caption
Here we can see the current size of the sprite.
Lets click the button and resize it.
///

![Sprite Scale Settings](img/step2-06.png)
/// caption
Set the width and height values to 32, and click "Apply".

If "Maintain Aspect Ratio" is checked, you will only have to change one of the values.
The other should follow suit.
///

![The Resized Sprite](img/step2-07.png)
///caption
Now our sprite is resized
///

Now we can create our player sprite!

## The Sprite Editor

Click on the "Edit Image" button on the left-hand side to open the Sprite Editor.

![Edit Sprite Button](img/step2-08.png)
/// caption
Open the Sprite Editor using the "Edit Image" button
///

![The Sprite Editor](img/step2-09.png)
/// caption
The Sprite Editor :eye::mouth::eye:
///

!!! quote annotate inline end

    If you get this reference, you get a cookie! 🍪 (1)

1.  Here's a hint: You gotta think with *Portals...*

Now, don't be alarmed, alright?
Although, if you do feel alarm, try to hold onto that feeling because that is the proper reaction to being told you have brain damage...

...or that you have to use the :simple-gamemaker: GameMaker Studio Sprite Editor...

In all seriousness, it's not as bad as it looks.

**Other options:**

-   [:simple-aseprite: Aseprite](https://www.aseprite.org/ "https://www.aseprite.org/")
-   [Pixilart.com](https://www.pixilart.com/ "https://www.pixilart.com/")
-   [Piscel](https://www.piskelapp.com/ "https://www.piskelapp.com/")


### The :material-grid-large: Grid Overlay

To make drawing symmetrical shapes easier, lets enable the grid overlay.
Simply click on the :material-grid-large: button to enable the grid, and use the drop-down menu to customise.

![The Grid Tool](img/step2-10.png)
/// caption
32 (sprite size) / 4 (grid size) = 8 (grid size in pixels)
///

### Common Tools

| Tool                                | Description                                               | Shortcut |
| ----------------------------------- | --------------------------------------------------------- | -------- |
| :material-pencil: Paintbrush        | Draw freely                                               | `D`      |
| :material-eraser: Erase             | Erase pixels back to transparent                          | `E`      |
| :material-format-color-fill: Fill   | Fill the selected area with colour                        | `F`      |
| :material-vector-line: Line         | Draws a line between 2 points                             | `L`      |
| :material-square-outline: Rectangle | Draws an outlined or filled rectangle                     | `R`      |
| :material-circle-outline: Ellipse   | Draws an outlined or filled ellipse                       | `C`      |
| :material-triangle-outline: Polygon | Draws an outlined or filled polygon with the given points | `P`      |
| :material-eyedropper: Colour Picker | Selects the colour of the selected pixel                  | `O`      |

## The Player

For the player, I used a few line segments to create a simple, triangular design.

![The Player Sprite](img/step2-11.png)
/// caption
"Here's one I made earlier :woman_tipping_hand:" ahh sprite
///

!!! note

    For a reason that is *far* above my pay grade, :simple-gamemaker: GameMaker Studio has 0^o^ facing toward the left, instead of upwards.
    This means you have to draw your sprites facing to the left if they are in a top-down perspective, like here.

## The Rest

Now that we have our player, we can create the shapes we are going to shoot.
Follow the same process as before to create 3 different sized shapes, and a bullet sprite.
Feel free to use a different sprite to make your shapes bigger.

![My 3 Shapes](img/step2-12.png)
/// caption
Small (32x32), Medium (64x64), Large (128x128), and the bullet (8x8)
///

## Sprite Origins

By default, sprites will have their origin point in the top-left corner.
If you expect the sprite to rotate around it's center, then we need to change the position of the origin point.

We can do this by clicking the drop-down menu in the top-right corner of the sprite window

![Changing Sprite Origin](img/step2-13.png)
/// caption
Here we can select 9 pre-defined positions for the origin.
You can select a custom location, but that's for another time.
///

Now, lets put these sprites to use!

## Objects

Lets start creating the player.
To do so, we need to create an Object, and name it "obj_player".

!!! tip

    Just like with sprites, objects follow :simple-gamemaker: GameMaker Studio's naming guidelines.
    Object names should *always* begin with "obj_" to signify that it is an object.

![Creating an Object](img/step2-14.png)
/// caption
Objects are made the same way as sprites, just use the correct folder,
///

![The Player Object](img/step2-15.png)
/// caption
Your created object should look like this. Don't be alarmed!
///

Now let's give the player the sprite we created earlier.
Click on the "No Sprite" button, and select the correct sprite from the popup.

![Selecting a Sprite](img/step2-16.png)
/// caption
It's like a mini File Explorer! awwwwwww :heart_eyes:
///

Now do this again a few more times:

-   **obj_bullet:** This is the bullet your player will fire.
    It should have it's sprite set to "spr_bullet"

-   **obj_shape:** This is the shape we will destroy with our bullets.
    It should have it's sprite set to "spr_shape_large".
    As we shoot at it, it will shrink.

-   **obj_game:** This is a "silent" object that will manage the game, draw UI, keep score, etc.
    This does not need a sprite.

![All the Objects](img/step2-17.png)
/// caption
This should be all the objects you need for this game.
///

Now, lets set up our room...