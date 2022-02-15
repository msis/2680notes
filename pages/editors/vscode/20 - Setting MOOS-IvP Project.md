# Setting your MOOS-IvP Project in `vscode`
!!! warning
	Make sure you have completed the setup steps [[10 - Setting things up#Install recommended extensions]], [[10 - Setting things up#Install code for your shell]].

In a terminal, open your project in `vscode`:
```bash
code moos-ivp-username
```

On the bottom right corner, the [[CMake]] extension will ask if you would like to configure the project. 
Choose `YES`.

It will ask you to choose a [[C++ Compiler]]. 
Choose the one the makes sense to you.

??? note
	If you weren't prompted to configure the project, you can click on the triangle inside a window icon on the left sidebar.

Open the `Command Palette` and call `CMake: Configure`.
This command will setup the auto-complete and other goodies.

