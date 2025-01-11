# Documenting your Code

[jsdoc]: https://jsdoc.app/
[feather]: https://manual.gamemaker.io/lts/en/Setting_Up_And_Version_Information/IDE_Preferences/Feather_Settings.htm
[feather-types]: https://manual.gamemaker.io/lts/en/The_Asset_Editors/Code_Editor_Properties/Feather_Data_Types.htm
[feather-forum]: https://forum.gamemaker.io/index.php?threads/feather-type-list.94619/

*There might be a right way*

It's important to know what you're doing.
It's good practice to comment your code so you can look back and ask yourself: "Why did I do that?"
(Believe me, trying to understand past me's code without comments is impossible)

## Functions

If you took N5 or Higher computing, and did any work with Javascript,
you may have noticed that GML looks a lot like it.
This is true even for documentation: :simple-gamemaker: GameMaker Studio uses [:simple-javascript: JSDoc][jsdoc], or at least parts of it.

``` javascript title="simple_math.gml"
/// @function 			add()
/// @description 		Adds two numbers.
/// @param {Real}	_a	The first number.
/// @param {Real}	_b	The second number.
/// @returns {Real}	
function add(_a, _b) {
	return _a + _b;
}
```

!!! quote "You, probably"

	But why would I write all that, when a simple sentence would be enough?

That's just it. We arn't writing these for you.
We write them like this so that the engine can read them.

:simple-gamemaker: GameMaker Studio will take these lines, and generate documentation for you.
Said documentation shows up in the editor to make your life easier:

- Shows parameter names at the bottom of the code editor window
- Full documentation when you hover over a function with your mouse
- Even [:material-feather: Feather][feather] uses the data to force parameter types.

As far as i've seen, these rules only apply to functions and constructors (arguably still functions).

---

<div class="grid" markdown>

The `@function` tag tells [:material-feather: Feather][feather] that this is a function. 
Note that this tag isn't required for the documentation to be generated, but just gives a hint.

``` javascript hl_lines="1"
/// @function 			add()
/// @description 		Adds two numbers.
/// @param {Real}	_a	The first value.
/// @param {Real}	_b	The second value.
/// @returns {Real}
function(_a, _b) {
	return _a + _b;
}
```

The `@description` tag allows you to provide... well, a description for the function.

``` javascript hl_lines="2"
/// @function 			add()
/// @description 		Adds two numbers.
/// @param {Real}	_a	The first value.
/// @param {Real}	_b	The second value.
/// @returns {Real}
function(_a, _b) {
	return _a + _b;
}
```

The `@param` tag allows you to provide the correct names and types of your function's parameters.
It also allows you to include a small description of said parameter.
The type of a parameter is included in the :material-code-braces: curly brackets. A list of valid types can be found in the [:simple-gamemaker: GameMaker Studio Manual][feather-types], or in [this forum post][feather-forum] from 2022.

``` javascript hl_lines="3 4"
/// @function 			add()
/// @description 		Adds two numbers.
/// @param {Real}	_a	The first value.
/// @param {Real}	_b	The second value.
/// @returns {Real}
function(_a, _b) {
	return _a + _b;
}
```

The `@returns` tag allows you to provide the type of return value. It's that simple.

``` javascript hl_lines="5"
/// @function 			add()
/// @description 		Adds two numbers.
/// @param {Real}	_a	The first value.
/// @param {Real}	_b	The second value.
/// @returns {Real}
function(_a, _b) {
	return _a + _b;
}
```

</div>