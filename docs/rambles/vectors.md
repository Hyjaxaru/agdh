# The :material-clock-outline: and :material-map-marker: for Vectors

[godotengine]:https://godotengine.org/

!!! note inline end

    This ramble is exclusive to :simple-gamemaker: GameMaker Studio.
    I'd recommend doing your own research before applying any of this to any other project.

If you've ever seen or used another game engine, such as [:simple-godotengine: Godot][godotengine],
You may have noticed that :simple-gamemaker: GameMaker Studio lacks the familiar vector type.

In most cases, this is fine. Objects provide `x` and `y` variables for their positions anyway.

***HOWEVER!***

If you find yourself doing something more complex, such as making your game's UI reactive.
Where the positions of different elements change quite a lot.
You might miss them.

Creating your own makeshift vectors can be done a number of ways in :simple-gamemaker: GameMaker Studio.

## Examples

| Method                | Rating                                                                                                |
| --------------------- | ----------------------------------------------------------------------------------------------------- |
| Arrays                | :material-star::material-star::material-star-outline::material-star-outline::material-star-outline:   |
| Structs               | :material-star::material-star::material-star::material-star-outline::material-star-outline:           |
| Constructor           | :material-star::material-star::material-star::material-star::material-star:                           |

=== "Arrays"
    ``` javascript
    // I don't think I need to explain lists
    position = [10, 10];

    x = position[0];
    y = position[1];

    magnitude = sqrt(power(position[0], 2) + power(position[1], 2));
    ```

=== "Structs"

    ``` javascript
    // structs look a little like Python dictionaries
    // or JSON data, if you're familiar
    position = {x: 10, y: 10};

    // we can then access the named values like this
    x = position.x;
    y = position.y;

    magnitude = sqrt(power(position.x, 2) + power(position.y, 2));
    ```

=== "Constructor"

    ``` javascript title="vector2.gml"
    // this usually goes in it's own script file
    function Vec2(_x=0, _y=0) constructor {
        x = _x;
        y = _y;

        static mag = function() {
            return sqrt(power(x, 2) + power(x, 2));
        }
    }
    ```

    ``` javascript title="Somewhere Else"
    // then in our code, we can call the constructor to give us a struct
    position = new Vec2(10, 10);

    // constructors return a pre-made struct
    // so we can use them just the same
    x = position.x;
    y = position.y;

    magnitude = position.mag();

    ```

!!! warning inline end
    
    There is a lot you can do to get close to a proper vector system in :simple-gamemaker: GameMaker Studio. However, it will never be perfect due to the engine's limitations.

All three of these methods will work just fine for any of your projects,
but constructors are closers to what you'd find in [:simple-godotengine: Godot][godotengine].
Constructors also have their own type that can be used in documentation. (See [:material-file-document: Documenting Your Code](../essentials/docs.md))

Structs and Constructors also allow you to include functions, like we just did for `Vec2().magnitude()`.

Personally, I prefer using Constructors, but it's up to you what you decide to use.
Remember that there isn't anything wrong with just using a few well named variables.
Objects still use separate `x` and `y` variables, so it's a good idea to follow that when doing player position, for example.
