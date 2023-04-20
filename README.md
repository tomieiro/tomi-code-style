# Tomi code style

... In current writing

This documents brings a code standard to Lua projects. In my GitHub, in repositories that are coded in Lua, this code style will be present.

## Line size, line end, wrapping.

*Maximum line size is 80 characters*.

Every line MUST end with ';' character. The exception is when a function, 'for' or 'if', are wrote in single line or a wrapped line, like:
```lua
local variable = "anything";
Tb = {};

function one()
    return "book";
end

function ok()
    if(Tb[1] == nil) then Tb[1] = 2 end
    for i,j in pairs(Tb) do print(i .. j) end
end

function Test() tb[1] = 2 end

```

### Wrapping
To line wrap, break the line in one point and next line gets a four spaces tabulation, like:
```lua
function checkSomething() return false end
function checkAnotherThing() return true end
function checkJustOneMore() return false end

local newVar = checkSomething() and
    checkAnotherThing() and
    checkJustOneMore();

print(newVar);

```

## Variables, functions and structures names convention

### Variables
To name a variable, be clear, that's it. Quite simple. Name it with a suggestive word that represents what variable will be used for.

For single name variables:

	- Global variable: Use capitalized names.
	- Local variable: Use all lowercase letters.
	- Private variables: Use a underscore followed by the variable name all lowercased.

For composite names:

	- Global variable: Use all first letters from each word capitalized.
	- Local variable: Use first word with all letters lowercased and all following words capitalized.
	- Private variables: Use a underscore followed by first word with all letters lowercased and all following words capitalized.

```lua
Testing = 100;
local another = 200;
MyVariable = 10;
local myLocalVariable = 20;

function func()
    scoped = 35;
    other = 55;
    myNotExplicitLocalFuncVariable = 15;
    local myLocalExplicitFuncVariable = 25;
end
```

Note that, third and fourth variables could be faced like global variables to this file, but, for other files that could use it, myLocalVariable will be not visible. So *when following a "local" keyword, variable will follow local variable style*.

### Functions

Functions follow the same pattern to names of variables. Just particular case is when the function is part of a table (in other words, method in a class, or a function in a table) the name always be written with the first word in lowercase and following words capitalized. Like:

```lua
function Bee()
    return "zzzz";
end

local function ant()
    return "crop crop";
end

ClassA = {}
local classB = {}

function ClassA:getNumber()
    return 4;
end

function classB:getNumber()
    return 5;
end

SimpleTable = {}

function SimpleTable.getAnotherNumber()
    return 8;
end

```

## Comments

Single-line comments could be written using '--' key.

Multi-line ones (Do not pretend that are single-line comments together, is a multi-line!) MUST be written in block, using '--[[' and '--]]' keys.

```lua
-- This is a single-line comment! So alone...
local a = "25 years";

--[[
This function will be awesome!
parameters: (int) a, (string) b
return: (int) 20
--]]
function awe(a, b)
    return 20;
end
```

## Imports and Filenames

All files must be named all words capitalized.

Leave all 'requires' in file beginning, and in alphabetical order.

Filename: Script.lua

```lua
require "LibA";
LibB = require "LibB";
local libC = require "LibC";
```
