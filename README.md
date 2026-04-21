## LÖVE2D VSCode Template

### A simple VSCode template for LÖVE2D.

### Requirements

* [Visual Studio Code](https://code.visualstudio.com/) or [VS Codium](https://vscodium.com/)
* [Love2D 11.5](https://love2d.org/)
* [Love-Build](https://github.com/ellraiser/love-build) v0.9
* [Lua Language Server by sumneko](https://marketplace.visualstudio.com/items?itemName=sumneko.lua)
* [Local Lua Debugger by Tom Blind](https://marketplace.visualstudio.com/items?itemName=tomblind.local-lua-debugger-vscode)

**Set Love2D and Love-Build in your PATH variable.**

### Setup

1. Download the repo as a .zip.
2. If you haven’t done so already, download the extensions required.
3. Configure build.lua to your liking.

### Running

Pressing F5 launches your game in debug mode. Here, you can use breakpoints and inspect your variables; this impacts performance.
You can switch to release mode in the “Run and Debug” tab (```Ctrl + shift + D```).

### Building

Press ```Ctrl + Shift + B```. To configure your build options, check build.lua in ```.\GAME```.

### Structure

```
├── /GAME
│   ├── /Assets      Contains the game's assets, i.e. SFX, sprites
│   ├── /Libraries   Contains external libraries, i.e. anim8
│   └── /Src         Contains the game's source code
│
├── /RESOURCES   Contains resources for you game that should not be shipped, like raw audio
│
└── /BUILDS          Contains the builds of your game made with makelove,
      ├── /LOVE      Contains builds in .love format
      └── /Binaries  Contains fused builds
```

### Appendix A: This seems an awful lot like the other template… What’s different?

It is. It’s based on [this](https://github.com/Keyslam/LOVE-VSCode-Game-Template). I’m extremely grateful to them for their work. However, due to the age of makelove, it has become harder to install with Python versions greater than 3.12. Due to that, I decided to create this repository which utilizes Love-Build instead of makelove and also adds an easy way to build with it.

### Appendix B: I want to do this too, but without your repository.

I’m not sure why you want to suffer unless I somehow got lazy with updating this when software eventually breaks, but here’s how.

1. Create a folder titled however you want.
2. In the folder, create a .vscode folder
3. Create a ```launch.json``` and ```tasks.json``` in the ```.vscode``` folder.
4. In ```launch.json```, input:
```
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "lua-local",
      "request": "launch",
      "name": "Debug",
      "program": {
        "command": "love"
      },
      "args": [
        "./GAME",
        "debug"
      ],
    },
    {
      "type": "lua-local",
      "request": "launch",
      "name": "Release",
      "program": {
        "command": "love"
      },
      "args": [
        "./GAME",
      ],
    },
  ]
}
```
5. In ```tasks.json```, input:
```
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Build with LÖVE-Build",
      "type": "shell",
      "command": "love-build", // Path to Love-build
      "args": ["./GAME/main.lua"],
      "group": "build",
    }
  ]
}
```
6. Exit the ```.vscode``` folder and create a new folder titled ```GAME```
7. In the ```GAME``` folder, create ```main.lua``` and ```build.lua```
8. Enter VSCode / VSCodium.
9. Press ```Ctrl + Shift + P```.
12. Type "Preferences: Open User Settings (JSON)
11. In that .json file, input:
```
{
	"Lua.workspace.library": [
		"${3rd}/love2d/library",
		"lib"
	],
	"Lua.runtime.version": "LuaJIT",
	"Lua.workspace.checkThirdParty": false,
}
```

You can utilize this as a base for adding further customizations
