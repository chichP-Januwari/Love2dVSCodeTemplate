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

### Appendix: This seems an awful lot like the other template… What’s different?

It is. It’s based on [this](https://github.com/Keyslam/LOVE-VSCode-Game-Template). I’m extremely grateful to them for their work. However, due to the age of makelove, it has become harder to install with Python versions greater than 3.12. Due to that, I decided to create this repository which utilizes Love-Build instead of makelove and also adds an easy way to build with it.