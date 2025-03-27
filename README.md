# GDLuau
> [!NOTE]  
> This is a fork of [GDLuau](https://github.com/Manonox/GDLuau) that I created to create some PRs for the upstream,
> but eventually will be spun out into and independent implementation to support extra specific features
> for sandboxed in-game code authoring and execution.
>
> Goals:
> - Implementation of the debugging API from Luau (also for use in the upstream).
> - Better documentation (also for use in the upstream).
> - Toolset for easy definition of native APIs to use in sandboxed code environments.
> - Luau ingame editor similar to Godot's native engine editor with highltighting and linting.
> - Code analysis tools.

A GDExtension that adds [Luau](https://luau-lang.org) C/C++ API bindings to GDScript
*(+ some extras)*

> [!IMPORTANT]
> This repository's `main` branch is only usable with
> [GDExtension](https://godotengine.org/article/introducing-gd-extensions)
> from Godot's `master` branch.

About
-----
GDLuau is for in-game scripting / UGC / modding.
*(This is **not** a replacement for or an alternative to GDScript.)*

Luau API closely follows Lua 5.1 API, you can find the manual [here](https://www.lua.org/manual/5.1/manual.html).<br />
For coding in lua/luau take a look at the ["Getting Started" section](https://luau-lang.org/getting-started) on [luau-lang.org](https://luau-lang.org).<br />


Features
--------
- Full C/C++ API in GDScript excluding lightuserdata/userdata
- Pushing/Pulling normal Callables (lambda Callables aren't supported)
- Pushing/Pulling Objects (Node / RefCounted) (as userdata)
- Pushing/Pulling Godot Arrays and Dictionaries
- Pushing/Pulling Godot Vector4s as Luau vectors
- Custom print implementation that emits a signal
- lua_loadstring, lua_dostring in GDScript (were "missing" in Luau)
- Configurable interrupt signal for run-away scripts (`while true do end`)


Compiling
------------
- Clone the repo with `--recursive` to also clone submodules
- Run `scons platform=<platform>` (also, preferably, add `use_mingw=yes`, if you have it installed)
- [A test project is included in the repo](https://github.com/Manonox/GDLuau/tree/master/demo)

---------------
[![lua logo](https://luau-lang.org/assets/images/luau.png)](https://luau-lang.org)<br />
