# Sidekick



## Scratch-Editor

![https://github.com/Menersar/Sidekick/blob/main/images/Scratch-Editor.png](https://github.com/Menersar/Sidekick/blob/main/images/Scratch-Editor.png)

- The Scratch editor is built up modularly from several repos.
- Each repo can stand alone.
- The main Repos are:
  - [GUI](scratch-gui)
  - VM
  - Scratch Blocks
  - Renderer
- There are also others, like scratch-storage and scratch-audio.

## [scratch-gui](https://github.com/LLK/scratch-gui)
- Wiki: https://github.com/LLK/scratch-gui.wiki.git
- React-based front end

## [scratch-vm](https://github.com/LLK/scratch-vm)
- Wiki: https://github.com/LLK/scratch-vm/wiki
- Manages state and does business logic. It sends the state to the GUI.
- Library for representing, running, and maintaining the state of computer programs written using Scratch Blocks.
- Defining Scratch extensions: 
https://github.com/LLK/scratch-vm/blob/develop/docs/extensions.md

## [scratch-blocks](https://github.com/LLK/scratch-blocks)
- Wiki: https://github.com/scratchfoundation/scratch-blocks.wiki.git
- branched from Blockly. This repo handles both the UI and logic for the portions of the editor that blocks appear in. Talks to the GUI, which often pipes things through to the VM.
- Library for building creative computing interfaces.
- Scratch Blocks is based on Google's Blockly project.

## [scratch-render](https://github.com/LLK/scratch-render)
- WebGL-based handler of what appears in the stage area. The GUI tells this what to do.
- WebGL-based rendering engine for Scratch 3.0




link repos.
