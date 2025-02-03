# Best Practice: Variables

If you're on this site *at all*, I'm sure you know what a variable is.
They store data!

Different languages have different ways of declaring them.
Here are a few examples

=== "Python"

    ```python
    # you can just say that x = y and a variable will be created:
    x = 10
    y = "Snake!"
    ```

=== "Javascript"

    ```javascript
    // both var and let declare variables that you can change
    var x = 10;
    let y = "Not Java"; // it's best practice to use let instead

    // const declares a value that you cannot change later, hence the name
    const z = 10;
    ```

=== "C++"

    ```c++
    // in C++, you use the variable type as the declaration
    int x = 15;
    bool y = true;
    ```

=== "Dart"

    ```dart
    // dart is very similar to C++. The type is the declaration
    int x = 10;
    String y = "Flutter? I hardly know her!";
    Array<int> z = [1, 2, 3];
    ```

However, :simple-gamemaker: GameMaker Language is a little different.
There are 3 ways of declaring variables.

## Global Variables

Of course, you can declare a `global` variable using the `global` keyword.
This will make the variable available to every object after it has been declared.

<div class="grid" markdown>

```javascript title="obj_game > Create" hl_lines="3"
global.kills = 0
global.player_name = "Neil"
global.ammo = 60
```

```javascript title="obj_player > Step" hl_lines="1"
if global.ammo > 0 {
    shoot_enemy() // pretend this does something...
}
```

</div>

!!! note
    It's best to declare `global` variables at the start of your game.
    Such as in the `Create` event of an object that it spawned first thing.
    This avoids potential issues if you try to call a `global` variable before it has been assigned.

