![EXAMPLE1](https://github.com/MrAmii/Matrix-CRT/raw/main/images/EXAMPLE1.png)

![EXAMPLE2](https://github.com/MrAmii/Matrix-CRT/raw/main/images/EXAMPLE2.png)

<a href="https://www.buymeacoffee.com/mramii" target="_blank">
  <img src="https://github.com/MrAmii/Matrix-CRT/raw/main/images/custom_bmac_matrix_button.png" alt="Click Me" style="background-color:rgba(255, 255, 255, 0); color: white; padding: 10px 20px; border: none; border-radius: 5px; cursor: pointer;">
</a>

<a href="https://github.com/MrAmii" target="_blank">
  <img src="https://github.com/MrAmii/Matrix-CRT/raw/main/images/GitHub_Logo.png" alt="Click Me" style="background-color:rgba(255, 255, 255, 0); color: white; padding: 10px 20px; border: none; border-radius: 5px; cursor: pointer;">
</a>

# After installation Guide

## Getting font, line numbers and terminal cursor blink

- Add the following to your settings.json

```json 
	"terminal.integrated.cursorBlinking": true,
	"editor.lineNumbers": "relative",

	"editor.fontFamily": "Fira Code, monospace",
	"terminal.integrated.fontFamily": "Fira Code, monospace",

	"editor.fontLigatures": true,
	"editor.fontWeight": "normal",
	"editor.fontSize": 13,
	"editor.lineHeight": 1,
	"editor.letterSpacing": 1, 
	"editor.cursorStyle": "line",
	"editor.cursorWidth": 2,
	"editor.cursorBlinking": "blink",
	"editor.renderWhitespace": "selection",
	"editor.renderControlCharacters": true,
	"editor.renderLineHighlight": "line",
	"editor.renderFinalNewline": "dimmed",
	
	"chat.editor.fontFamily": "Fira Code, monospace",
	"chat.editor.fontSize": 13,
```


 
- navigate there by entering "The Command Palette" by pressing Ctrl+Shift+p and typing settings and selecting Preferences: User settings(JSON), then paste the following block in respecting the structures already present.

#### You will be using this command often in the future, alternatively if  you click the drop down menu and press >
*There are still aspects that do not have Fira Code font applied yet. The Editor and Terminal should, if not you may need to install [Fira Code](https://github.com/tonsky/FiraCode)*


## Create glowing text effect and final application of Fira Code

- Navigate to the extension [Custom CSS and JS Loader](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css)
> **WARNING** Read the description and warnings of <u>Costume CSS and JS Loader</u> extension, use at your own risk.
- Create a directory (folder) named after the extension wherever you would like, I put mine within the Visual Studio Code folder in Documents.
- Create a new file in VSCode named custom.css and save it there.
- In the file paste the following.
- In the file paste the following.

```css
/* Variable for text shadow color */
:root {
    --text-shadow-color: #00ff4034;
}

/* Apply glow effect to all text in the editor */
.monaco-editor .mtk {
    text-shadow: 0 0 2px var(--text-shadow-color), 0 0 4px var(--text-shadow-color), 0 0 6px var(--text-shadow-color);
}

/* Apply glow effect to all text in the entire VS Code UI */
* {
    text-shadow: 0 0 2px var(--text-shadow-color), 0 0 4px var(--text-shadow-color), 0 0 6px var(--text-shadow-color);
}

/* Reduce glow effect for italic text */
.monaco-editor .mtk.italic, .monaco-editor .mtki {
    text-shadow: 0 0 2px var(--text-shadow-color), 0 0 5px var(--text-shadow-color);
}

/* Apply glow effect to pasted text */
.monaco-editor .mtk.pasted {
    text-shadow: 0 0 5px var(--text-shadow-color), 0 0 10px var(--text-shadow-color), 0 0 15px var(--text-shadow-color);
}

/* Apply Fira Code font to all text elements except buttons 
body */
.monaco-editor, 
.monaco-editor .mtk, 
.monaco-menu .action-item .action-label, 
.monaco-menu .monaco-action-bar .action-item .action-label, 
.monaco-menu .monaco-action-bar .action-item .keybinding, 
.monaco-menu .monaco-action-bar .action-item .submenu-indicator, 
.menubar-menu-button, 
.explorer-viewlet .monaco-list-row .label-name, 
.explorer-viewlet .monaco-list-row .label-description, 
.explorer-viewlet .monaco-list-row .label-details, 
.chat-view .message, 
.chat-view .message-content, 
.chat-view .monaco-editor .view-line {
    font-family: 'Fira Code', monospace !important;
}

/* Apply Fira Code font to the status bar */
.statusbar-item {
	font-family: 'Fira Code', monospace !important;
}

/* Apply Fira Code font to the activity bar (search, debug, extensions, source control) */
.activity-bar .monaco-action-bar .action-item .action-label {
	font-family: 'Fira Code', monospace !important;
}
```

- Save and then in the settings.json add
```json
    "vscode_custom_css.imports": [
        "file:///C:/Users/%USERNAME%/Documents/Visual Studio Code/Custom CSS and JS Loader/custom.css"
    ],
```
>**Correct these directions to fit your own**

- Now save the file and open the Command Palette and type <u>Reload Custom CSS and JS</u>

 *You should now have glowing text*

#### You can edit the effect by changing the variable --text-shadow-color or by increasing the third element of each px, basically wherever you see a number followed by px, that number is what you change. Text shadow allows you to stack multiple shadow effects, so with this logic the smallest one has three stacked making it slightly brighter than the second and third, giving a blooming effect. I prefer a more subtle effect but you may want it brighter.

## Add a CRT Texture Foreground

- Install extension [Background](https://marketplace.visualstudio.com/items?itemName=Katsute.code-background)
(Funny thing about it is that its not so much a background that it applys as it is a foreground, but that is exactly the effect I needed to make this work)

#### A CRT Texture has been added with this extension, it will be located along with the extensions resources at:

```
    C:/Users/{YOURUSERNAME}/.vscode/extensions/mramii.matrix-crt-vscode-theme-0.0.1/images/matrix_crt_1.png
```


- The name of this extensions folder may be different depending on what version it is currently at
so just navigate to the extensions folder manually.

- At the bottom left of your screen you will see Background, press that and it will open up the Background extensions menu. Alternatively you could type <u>Background: Configuration</u> in the command palette.

- Select window

- Select file and navigate to the matrix_crt_1.png

- Set opacity anywhere between 0.05 to 0.1 is my recommendation

- Set repeat to repeat and then save

- To remove the texture Ctrl+Shift+p and type 

*You should have a the CRT texture applied to the whole of your window.*

> **WARNING: If a problem occurs where you cannot update the opacity or you uninstall the addon and the effect persists, in the command palette type <u>Background: Uninstall</u>  The extension may need to still be installed, if so then reinstall and trying again**

# EXTRA EFFECT

## To achieve trailing cursor effect

- Navigating to https://github.com/qwreey/dotfiles/blob/master/vscode/trailCursorEffect/index.js
 
- Download it or copy paste it into a new index.js that you will place along side the custom.css

- At the top of that script it calls const color, replace that hex code with #008F11. (Ignore the color box, it is automatically applied when a hex color code is detected in your code)
 
- now navigate back to your settings.json and update it to reflect the new file Custom CSS and JS will call on. It will look like this:

```json
    "vscode_custom_css.imports": [
        "file:///C:/Users/%USERNAME%/Documents/Visual Studio Code/Custom CSS and JS Loader/custom.css"
        "file:///C:/Users/%USERNAME%/Documents/Visual Studio Code/Custom CSS and JS Loader/index.js"
    ],
```

 *Reload Custom CSS and JS, you should now have the cursor effect*
 >**Be sure to leave automatic update ticked, as I wil be working on fine tuning colors and getting the rest of the UI to be uniformly in Fira Code if possible**

# *"Welcome to the real world" -Morpheus* #
