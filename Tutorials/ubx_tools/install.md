---
layout: page
title: Install ubx_tools
---

___NOTE___: __ubx_tools__ works locally, that is running from the root folder of the project.
However, the following guide shows an easy way to install it on your computer, such that you can use it from anywhere!

___NOTE (2)___: The following installation guide conforms to the [ubx_installation_layout](). However, it is not the goal of Microblx framework to impose an installation layout to you. If you are an advance user, you can easily create your own installation script.

## Installation steps

- First of all, we assume you have already Microblx properly installed and your environment already setup as explained in the [quickstart guide](/Quickstart)
- Download the source code from github
```sh
$ git clone git://github.com/haianos/microblx_cmake
```

- (Optional, but suggested) Setup tue ___UBX_INSTALL___ environment variable to point to your install path, that is
```sh
$ export UBX_INSTALL=<your-install-path>
```
- Run the ___install___ script. It will check if the previous steps have been done properly (environment sane)
- The script will ask if you want to create symlink to the scripts. It is suggested to create them.
- Set your ___PATH___ variable such that it includes also the microblx executable path, that is
```sh
$ export PATH=$UBX_INSTALL/bin
```
- Set your ___LUA_PATH___, such that Lua knows where to fetch Microblx Lua modules and scripts
```sh
$ export LUA_PATH=";;;$LUA_PATH;$UBX_INSTALL/share/ubx/scripts"
```
- setup ___UBX_METAMODELS__ environment path correctly. Usually
```sh
$ export UBX_METAMODELS=$UBX_INSTALL/share/ubx/metamodels
```

## New Tools Available

After installation, the following tools will be available:

* ubx_pkg_gen: Code generation tool for package/software development
* ubx_capp_gen: Code generation tool for generating a C-based app starting from an USC file.