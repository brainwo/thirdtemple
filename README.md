### Development

This instruction below is a recommended way to develop this project. However it's not mandatory, you can skip to [here](#building).

#### Editor setup

To make things easier, use [clangd](https://github.com/clangd/clangd) in your editor of choice. Below is how you install clangd language server in coc.nvim:

```
CocInstall coc-clangd
```

Once installed, you will need [`bear`](https://github.com/rizsotto/Bear) to generate `compile_commands.json` that used for libraries definition and stuff. [More info](https://clangd.llvm.org/installation.html#project-setup) on how to set it up.

To install `bear`, e.g. on Arch Linux:

```
yay -S citra-bin
```

Then generate the file using `bear`:

```
bear -- make
```

#### Running and debugging

Use [Citra](citra-emu.org/) to run the 3ds binary. It's recommended to install the `citra-qt` to make it easier to change stuff and reloading project. Installation on Arch Linux:

```
yay -S citra-qt-bin
```

Some useful hotkeys to use:

| Key        | Action         |
| ---------- | -------------- |
| `Ctrl` `p` | screenshot     |
| `F6`       | reload project |
| `F8`       | rotate screen  |

To help it debug faster you can use [`watchexec`](https://github.com/watchexec/watchexec) to automatically build on source code changes. Installation on Arch Linux:

```
yay -S watchexec
```

To start source code watching on the project directory:

```
watchexec -e c make
```

Now you can reload your project and see immediate result.

<h4 id='building' class='anchor' aria-hidden='true'>Building .3dsx</h4>

```
make
```

#### Building .cia

TODO

#### Bonus

To make it easier to transferring the compiled file to your 3DS, try this [CLI program](https://github.com/brainwo/ftunnel) I made. It generates a temporary QR code URL to download the file to your 3DS through tunnel. It works when your PC and 3DS don't connect to the same network. Use it to host `.cia` file then use FBI app on your 3DS to download the `.cia` file and this app will be installed on your 3DS.

### License

This software is licensed under the GNU General Public License v3 license. Refer to the provided LICENSE file for further information.
