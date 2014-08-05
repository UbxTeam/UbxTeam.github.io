---
layout: page
title: Layout and Environment Variables
---

This document describes the default layout suggested for the installation and used by ubx_tools.
A set of environment variables is listed above, referring to the installation layout.
Remember that it is not necessary to install Ubx software, but it is possible to run it locally.

<font size="4" color="#0066FF"><b>NOTE:</b></font>The goal of Microblx is not to impose a particular layout. Feel free to change it, and have your own. We just propose a possible solution as starting point, because we found handy to have a common starting point. Furthermore, several projects about software distribution exists out of there, and we don't want to re-invent the wheel.

<font size="4" color="#CC0000"><b>NOTE:</b></font>The Environment Variables mentioned here may be subject of changes in the near future. Please, check this page often if any change has been applied.


## Installation Layout

Given a desidered installation folder ```<install-path>```, Ubx can be installed as follow:

    | ~<install-path>
    | - /bin
    | - /include
    | | - ubx/
    |   | - types/
    |
    | - /lib
    | | - ubx/
    |   | - blocks/
    |   | - types/
    |
    | - /share
    | | - ubx/
    |   | - cmake/
    |   | - templates/
    |   | - models/
    |   | - metamodels/
    |   | - scripts/
    
### Folders description

| Folder | Contains |
| -------------|----------------|
| /bin    | generated executable ubx applications and symlinks to executable scripts) |
| /include/ubx | type headers (needed only for dev-purpose)| 
| /lib/ubx/types | Type-only modules | 
| /lib/ubx/blocks | Blocks-only modules | 
| /share/ubx/cmake | CMake modules (to find dependencies) | 
| /share/ubx/templates | Templates for code generation | 
| /share/ubx/models | Block models (.blx) of implemented blocks |
| /share/ubx/metamodels | Metamodels specifications |
| /share/ubx/scripts | (Lua) scripts and modules |

## Environment Variables

|  Var. Name    |   Description  | Default |
| -------------|----------------|----------------|
| UBX_ROOT  | Points to Microblx root repository folder | ```$ export UBX_ROOT=<ubx-core>``` |
| UBX_INSTALL  | Points to install root folder | ```$ export UBX_INSTALL=<install-path>``` |
| UBX_MODULES  | -> lib/ubx | ```$ export UBX_MODULES=$UBX_INSTALL/share/ubx/modules```|
| UBX_MODELS   | -> share/ubx/models | ```$ export UBX_MODULES=$UBX_INSTALL/share/ubx/models```|
| UBX_METAMODELS | -> share/ubx/metamodels |  ```$ export UBX_METAMODELS=$UBX_INSTALL/share/ubx/metamodels```|

___NOTE:___ Most of the environment variables can be deduced from ```UBX_INSTALL```. However, this allows to override a default option, while keeping the others.

___NOTE (2):___ In the future, these Environment Variables will be treated as list of paths!

## Environment Settings

The following Environment are system-dependent and they must be setup properly

|  Var. Name    |   Description  | Default |
| -------------|----------------|----------------|
| PATH  | Add to this the /bin folder(s) | ```$ export PATH=$PATH:<install-path>/bin``` |
| LUA_PATH  | Add /script folder from both installation and Ubx core | ```$ export LUA_PATH=";;;$LUA_PATH:<install-path>/share/ubx/scripts/?.lua;<ubx-core>/lua/?.lua``` |
| CMAKE_PREFIX_PATH | Add /cmake folder to find cmake modules | ```$ export CMAKE_PREFIX_PATH=$CMAKE_PREFIX_PATH:$UBX_ROOT/share/ubx/cmake``` |