# OpenComputers Miner

This is a fully modular software for an open computers mining robot

## Features

* Digs a tunnel with an height of two blocks
* Places torches
* Places chests
* Puts all found ores in the chests
* Disposes insignificant items (e.g. cobblestone)
* Builds a bridge when necessary
* Stable behavior in case of mobs, falling blocks like grave etc.
* Different mining patterns available

## Todo

* UI
* Startup routine
* Create detailed documentation of the modules here in the readme

## Known bugs

* Interference between the placement of torches and stone when building bridges

## Modules

The code is fully functional and modular. The functions and variables are located in different modules. Non of the modules are executed on itself, they only provide functions to the main module which defines the starting point of the program. These are the currently available modules:

### Header

Imports all the necessary components which are used in the subsequent modules. Always import this first 

### Inventory

Handles all the inventory management. Is imported as "invHelper"

### Movement

The movement module is responsible for stable and highly error tolerant movement and digging

### Zigzag

This module contains all the functions for the "zigzag" mining pattern

### Plain

This module contains all the functions for the "plain" mining pattern (which is basically no pattern at all)

### Square

This module contains the functions for the "square" mining pattern. 
</br>
It mines a whole of the specified square size.

### Main

This is where the software starts. The modules are imported and subsequently executed here

### Interface
The interface is called at system start.

1. asks whether the robot should start mining
2. choose a mining pattern
3. specify the size of the mining area


## Usage
In order to use the Interface to start the robot one needs to specify the correct path to the starting module (e.g. /mypath/MAIN.lua) inside the interface script.
<br/>
<br/>
How to enable the automatic interface start by system start:
<br/>
1. start the robot and type "install" in the root directory<br/>
2. you will be asked what you want to install, choose openOS<br/>
3. name your interface file (or the file you want to autostart) "autorun.lua"<br/>
4. specify the path to your autorun.lua file under /home/.shrc<br/>

Reference:<br/>
https://github.com/MightyPirates/OpenComputers/issues/2171#issuecomment-266532559 <br/>
