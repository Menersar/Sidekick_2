# Sidekick



## Scratch Editor

- Getting Started: https://github.com/LLK/scratch-gui/wiki/Getting-Started
<p  align="center">
		<img src="/images/Scratch-Editor.png" style="width: 50%">
</p>

Design of the Scratch editor interface (`GUI`): [https://en.scratch-wiki.info/wiki/User_Interface](https://en.scratch-wiki.info/wiki/User_Interface)
<p  align="center">
		<img src="/images/Scratch_3.0_program_sections.png" style="width: 50%">
</p>

- The `Scratch Editor` is built up modularly from several repos.
- Each repo can stand alone.
- The main Repos are:
  - [GUI](#scratch-gui)
  - [VM](#scratch-vm)
  - [Blocks](#scratch-blocks)
  - [Renderer](#scratch-render)
  - [Desktop](#scratch-desktop)
- There are also others, like `scratch-storage` and `scratch-audio`.

## [scratch-gui](https://github.com/LLK/scratch-gui)
- Wiki: https://github.com/LLK/scratch-gui/wiki
- React-based front end.
- Graphical User Interface for creating and running Scratch 3.0 projects.
- A set of React components that comprise the `GUI` for creating and running Scratch 3.0 projects

## [scratch-vm](https://github.com/LLK/scratch-vm)
- Wiki: https://github.com/LLK/scratch-vm/wiki
- Defining Scratch extensions: https://github.com/LLK/scratch-vm/blob/develop/docs/extensions.md
- Library for representing, running, and maintaining the state of computer programs written using [Scratch Blocks](#scratch-blocks).
  - It sends the state to the `GUI`.

## [scratch-blocks](https://github.com/LLK/scratch-blocks)
- Wiki: https://github.com/scratchfoundation/scratch-blocks/wiki
- Branched from and based on Google's [Blockly](https://developers.google.com/blockly) project.
- Fork of Google's [Blockly](https://github.com/google/blockly) project that provides a design specification and codebase for building creative computing interfaces.
- Library for building creative computing interfaces.
- Together with the [Scratch VM](#scratch-vm) this codebase allows for the rapid design and development of visual programming interfaces.
- Repo handles the **UI** and **logic** for the portions of the editor that blocks appear in. 
   - Talks to the `GUI`, which often pipes things through to the [VM](#scratch-vm).

## [scratch-render](https://github.com/LLK/scratch-render)
- WebGL-based rendering engine for Scratch 3.0.
- Handler of what appears in the `Stage Area`.
- The `GUI` tells this what to do.

## [scratch-desktop](https://github.com/LLK/scratch-desktop)
- Scratch 3.0 as a self-contained desktop standalone application.
- Note: The `scratch-desktop` branch of [scratch-gui](#scratch-gui) was used during development of the Scratch Desktop App.
	- It held a few changes necessary for the Scratch app to function correctly, but are not yet merged into the main development branch.
