# lua-loader

Make require() in lua to load lua [bower](http://bower.io) components as lua modules

## Usage

### 0. Bower
Download and install [Node.js](http://nodejs.org/download/). Then you have `npm`.
Now do `npm install -g bower`

### 1. Install
In the root of your project, `bower install --save require`

### 2. Initialise
At the start of the main lua file in your project, enable lua-loader as follows:
```lua
require("vendor.require.index")(function() end)
```
(It's initialised a bit magically with a dummy function that will point it to where the root of the project is.
Don't worry, just type it as above, and aftwerwards everything will look just normal)

### 3. Require what you need
Install the bower package you want to use in your project, eg. `bower install log`.
This will install the package as expected in `./vendor/log`.
You can now just:
```lua
local log = require("log")
```
And then just use the module for what it's useful for, eg:
```lua
log({text = "Hello, world!"})
```

## Limitations
- Doesn't read the `bower.json`. So won't respect the `main` entry in there. Tries to load `./index.lua` or else `./<package name>.lua` and that's it.

## License
[LGPL+](https://github.com/wscherphof/lua-loader/blob/master/LICENSE.md)
