[VSCode](https://code.visualstudio.com/) is a text-editor from Microsoft.
It has very little to do with Visual Studio but the name.

!!! Note
	Saad is very biased here as this is the editor he uses everyday.

## Setup
### Install `vscode`
It can be installed either from the [official webpage](https://code.visualstudio.com/Download) or with Homebrew:
```bash
brew instal visual-studio-code
```

### Install recommended extensions
??? tip "Keyboard shortcut"
	Open the extension menu: ++shift+meta+e++

- `ms-vscode.cpptools-extension-pack`
- `ms-vsliveshare.vsliveshare-pack`

### Setup `bash` as default shell for `vscode`
Open the `Command Palette` and type: `default profile`.
This should only keep one command like `Terminal: Select Default Profile`. Select `bash` as the default shell.

??? tip "Keyboard shortcut"
	Command Paletter: ++shift+meta+p++

### Install `code`  for your shell
In the `Command Palette` type: `install code`. 
This should only keep one command like `Shell Command: Install 'code' in shell PATH`

### Install MOOS Syntax highlighting
Download this file [moos-ivp-editor-0.2.0.vsix](./moos-ivp-editor-0.2.0.vsix)
In the directory where you downladed the file above, call this command in a terminal:
```bash
code --install-extension moos-ivp-editor-0.2.0.vsix
```

