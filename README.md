# Sidekick

<!-- <details open> -->
<details>
<summary>

# Contents

	
### Example: Download, link and install `scratch-desktop`, `scratch-gui`, `scratch-vm` and `scratch-blocks`. <a name="h1-2-1"></a>

</summary>

<ul>
	<li> <a href="#h0">Information</a>
		<ul>
			<li><a href="#h0-1">Scratch Editor</a>
				<ul>
					<li><a href="#h0-1-1">scratch-desktop</a></li>
					<li><a href="#h0-1-2">scratch-gui</a></li>
					<li><a href="#h0-1-3">scratch-vm</a></li>
					<li><a href="#h0-1-4">scratch-blocks</a></li>
					<li><a href="#h0-1-5">scratch-render</a></li>
				</ul>
			</li>
		</ul>
	</li>
	<li> <a href="#h1">Implementation</a> 
		<ul>
			<li><a href="#h1-1">Entwicklungsumgebung vorbereiten</a>
				<ul>
					<li><a href="#h1-1-1">RASPBERRY-PI-OS</a></li>
					<li><a href="#h1-1-2">WINDOWS 10, 11</a></li>
				</ul>
			</li>
			<li><a href="#h1-2">Prepare Scratch Projects</a>
				<ul>
					<li><a href="#h1-2-1">Download, link and install projects </a></li>
					<li><a href="#h1-2-2">Run `scratch-desktop` in development mode </a></li>
					<li><a href="#h1-2-3">Make a project __ build </a></li>
					<li><a href="#h1-2-4">Make a project packaged build </a></li>
				</ul>
			</li>
		</ul>
	</li>
<ul>
	
</details>

# Information  <a name="h0"></a>
## Scratch Editor <a name="h0-1"></a>

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
  - [Desktop](#scratch-desktop)
  - [GUI](#scratch-gui)
  - [VM](#scratch-vm)
  - [Blocks](#scratch-blocks)
  - [Renderer](#scratch-render)
- There are also others, like `scratch-storage` and `scratch-audio`.
	
### [scratch-desktop](https://github.com/LLK/scratch-desktop) <a name="h0-1-1"></a>
- Scratch 3.0 as a self-contained desktop standalone application.
- Note: The `scratch-desktop` branch of [scratch-gui](#scratch-gui) was used during development of the Scratch Desktop App.
	- It held a few changes necessary for the Scratch app to function correctly, but are not yet merged into the main development branch.

### [scratch-gui](https://github.com/LLK/scratch-gui/tree/scratch-desktop) <a name="h0-1-2"></a>
- Wiki: https://github.com/LLK/scratch-gui/wiki
- React-based front end.
- Graphical User Interface for creating and running Scratch 3.0 projects.
- A set of React components that comprise the `GUI` for creating and running Scratch 3.0 projects

### [scratch-vm](https://github.com/LLK/scratch-vm) <a name="h0-1-3"></a>
- Wiki: https://github.com/LLK/scratch-vm/wiki
- Defining Scratch extensions: https://github.com/LLK/scratch-vm/blob/develop/docs/extensions.md
- Library for representing, running, and maintaining the state of computer programs written using [Scratch Blocks](#scratch-blocks).
  - It sends the state to the `GUI`.

### [scratch-blocks](https://github.com/LLK/scratch-blocks) <a name="h0-1-4"></a>
- Wiki: https://github.com/scratchfoundation/scratch-blocks/wiki
- Branched from and based on Google's [Blockly](https://developers.google.com/blockly) project.
- Fork of Google's [Blockly](https://github.com/google/blockly) project that provides a design specification and codebase for building creative computing interfaces.
- Library for building creative computing interfaces.
- Together with the [Scratch VM](#scratch-vm) this codebase allows for the rapid design and development of visual programming interfaces.
- Repo handles the **UI** and **logic** for the portions of the editor that blocks appear in. 
   - Talks to the `GUI`, which often pipes things through to the [VM](#scratch-vm).

### [scratch-render](https://github.com/LLK/scratch-render) <a name="h0-1-5"></a>
- WebGL-based rendering engine for Scratch 3.0.
- Handler of what appears in the `Stage Area`.
- The `GUI` tells this what to do.


# Implementation <a name="h1"></a>
## ENTWICKLUNGSUMGEBUNG VORBEREITEN <a name="h1-1"></a>

### – RASPBERRY-PI-OS – <a name="h1-1-1"></a>
	
- [ ] Optional: Bereinigen des `npm`-Cache und Entfernen von `NodeJS` und `npm` vom System.
```console
sudo npm cache clean --force
sudo apt remove nodejs npm
```

- [ ] Installieren des `npm`-Version-Managers, `n`, und damit Neuinstallieren von `NodeJS v16.0.0`.
```console
sudo npm install --global n
sudo n 16.0.0
```

- [ ] Optional: Überprüfen der `NodeJS`-Version. <br />
(Ausgabe sollte `v16.0.0` zurückgeben.)
```console
node --version
```

- [ ] Installiernen von `yarn`. <br />
(Viele Anleitungen verwenden `npm`; zuverlässig hat es bei mir mit `yarn` funktioniert.)
```console
sudo npm install --global yarn
```

- [ ] Herunterladen und Entpacken des GitHub-Repositories `scratch-extension`. <br />
https://github.com/Menersar/scratch-extensions

---

### – WINDOWS 10, 11 – <a name="h1-1-2"></a>

- [ ] Optional: Deinstallieren von `NodeJS`. <br />
```console
winget uninstall Node.js
```

- [ ] Installieren von `NodeJS v16.0.0`. <br />
```console
winget install OpenJS.NodeJS --version 16.0.0
```

- [ ] Optional: Überprüfen der `NodeJS`-Version. <br />
(Ausgabe sollte `v16.0.0` zurückgeben.)
```console
node --version
```

- [ ] Installieren von `yarn`. <br />
(Viele Anleitungen verwenden `npm`; zuverlässig hat es bei mir mit `yarn` funktioniert.)
```console
winget install Yarn.Yarn
```

- [ ] Installieren von `webpack` mit `yarn`. <br />
(Hauptsächlich verwendet, um JavaScript-Dateien für Browsernutzung zu bündeln.)
```console
yarn add webpack --dev
```

- [ ] Herunterladen und Entpacken des GitHub-Repositories `scratch-extension`. <br />
https://github.com/Menersar/scratch-extensions

<br />

	
	

## Prepare Scratch Projects <a name="h1-2"></a>

### Download, link and install projects <a name="h1-2-1"></a>
Example: Download, link and install `scratch-desktop`, `scratch-gui`, `scratch-vm` and `scratch-blocks`.

<details>

<summary>
	Commands:	
</summary>


```shell
mkdir Scratch
```

```shell
cd Scratch
```

```shell
git clone https://github.com/llk/scratch-desktop # if making changes fork the project and check out your copy
```

```shell
git clone https://github.com/llk/scratch-gui # if making changes fork the project and check out your copy
```

```shell
git clone https://github.com/llk/scratch-vm # if making changes fork the project and check out your copy
```

```shell
git clone https://github.com/llk/scratch-blocks # if making changes fork the project and check out your copy
```

```shell
cd scratch-vm
```

```shell
npm install
```

```shell
npm link
```

```shell
cd ../scratch-blocks
```

```shell
npm install
```

```shell
npm link
```

```shell
cd ../scratch-gui
```

```shell
npm install
```

```shell
npm link
```

```shell
cd ../scratch-desktop
```

```shell
npm link scratch-vm scratch-blocks scratch-gui
```

```shell
npm install
```

</details>


<br />


### Run project in development mode <a name="h1-2-2"></a>

Example: Run `scratch-desktop` in development mode.

<details>

<summary>
	Commands:	
</summary>

```shell
npm start
```
	
</details>
	

<br />
	
	
### Make a project build <a name="h1-2-3"></a>
	
Example: Make a `scratch-desktop`__ build.

<details>

<summary>
	Commands:	
</summary>
	
```shell
npm run dist
```

</details>
	

<br />


### Make a project packaged build <a name="h1-2-4"></a>
	
Example: Make a `scratch-desktop` packaged build.

<details>

<summary>
	Commands:	
</summary>
	
```shell
npm run dist
```

</details>

	
	

	
Troubleshooting
If you run into npm install errors, try these steps:

run npm cache clean --force
Delete the node_modules directory
Delete package-lock.json
run npm install again
	
	
	

This document describes technical topics related to Scratch 3.0 extension development, including the Scratch 3.0 extension specification:
https://github.com/LLK/scratch-vm/blob/develop/docs/extensions.md
	
block-types
https://medium.com/@hiroyuki.osaki/scratch-3-block-types-you-can-develop-and-samples-191b0d769b91
