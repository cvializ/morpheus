morpheus
========

A JavaScript/ECMAScript5 interpreter written for the MorpheusScript engine in [Medal of Honor Allied Assault](https://en.wikipedia.org/wiki/Medal_of_Honor:_Allied_Assault).

This project is based heavily on [NeilFraser/JS-Interpreter](https://github.com/NeilFraser/JS-Interpreter)

Prerequisites
-------------

You need an installation of Medal of Honor Allied Assault to run the Interpreter. I got my copy from [GOG Games](https://www.gog.com/game/medal_of_honor_allied_assault_war_chest).

MOHAA is made for Windows, but GOG has a convenient Linux downloader that works nicely with PlayOnLinux.

It will help to play the game with the Developer Console enabled.
You can enable it using the in-game Settings menu, selecting Advanced, and checking Enable Developer Console.

Installation
------------

To install the interpreter, clone this repo and copy-paste the files into the MOHAA/main directory.

```bash
MOHAA="/home/user/path/to/mohaa"
git clone https://github.com/cvializ/morpheus
cp -r morpheus/* "$MOHAA/main/"
```

Usage
-----

Run your JavaScript into the [acorn-msan](https://github.com/cvializ/acorn-msan) converter.

```bash
npm install -g acorn-msan
cd "$MOHAA/main"
echo 'var x = 42; var y = 42; var z = 42; x * y * z;' > maps/dm/test.js
acorn-msan --infile maps/dm/test.scr --outfile maps/dm/ast.scr
```

Run the game and open the Developer Consoler by pressing the backtick key (\`).
Type `map dm/mohdm1`.

After the map loads, you should see in the console output the text `74088` somewhere near the bottom of the output. You just ran JavaScript in a video game from 2002.

There is still a lot left to implement, so only a subset of features currently work.

Todo
----


- Function calls
- Built-in objects
- The `new` keyword
- etc
