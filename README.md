# Tomi code style

... In current writing

This documents brings a code standard to Lua projects. In my GitHub, in repositories that are coded in Lua, this code style will be present.

## Line size, line end, wrapping.

*Maximum line size is 80 characters*.

Every line MUST end with ';' character. The exception is when a function, 'for' or 'if', are wrote in single line, like:
```lua
local variable = "anything"
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
    checkJustOneMore()

print(newVar)

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

Function follow the same pattern to names of variables. The
