# Sidekick



## Scratch-Editor

- Getting Started: https://github.com/LLK/scratch-gui/wiki/Getting-Started

![https://github.com/Menersar/Sidekick/blob/main/images/Scratch-Editor.png](https://github.com/Menersar/Sidekick/blob/main/images/Scratch-Editor.png)

- The Scratch editor is built up modularly from several repos.
- Each repo can stand alone.
- The main Repos are:
  - [GUI](#scratch-gui)
  - [VM](#scratch-vm)
  - [Blocks](#scratch-blocks)
  - [Renderer](#scratch-render)
- There are also others, like scratch-storage and scratch-audio.

## [scratch-gui](https://github.com/LLK/scratch-gui)
- Wiki: https://github.com/LLK/scratch-gui/wiki
- React-based front end.

## [scratch-vm](https://github.com/LLK/scratch-vm)
- Wiki: https://github.com/LLK/scratch-vm/wiki
- Manages state and does business logic. 
- It sends the state to the `GUI`.
- Library for representing, running, and maintaining the state of computer programs written using [Scratch Blocks](#scratch-blocks).
- Defining Scratch extensions: 
https://github.com/LLK/scratch-vm/blob/develop/docs/extensions.md

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
- Handler of what appears in the stage area.
- The `GUI` tells this what to do.
