![Example Fullscreen](https://github.com/MrAmii/Matrix-CRT-vscode-theme/blob/main/images/EXAMPLE2.png) 

![Example Closeup](https://github.com/MrAmii/Matrix-CRT-vscode-theme/blob/main/images/EXAMPLE2.png) 

<a href="https://www.buymeacoffee.com/mramii" target="_blank"><img src="https://github.com/MrAmii/Matrix-CRT-vscode-theme/blob/main/images/custom_bmac_matrix_button.png" alt="Buy Me A Coffee" height="41" width="174"></a>

<script async defer src="https://buttons.github.io/buttons.js"></script>

<a class="github-button" href="https://github.com/MrAmii" data-color-scheme="no-preference: dark; light: dark; dark: dark;" data-size="large" aria-label="Follow @MrAmii on GitHub">Follow @MrAmii</a>

<a class="github-button" href="https://github.com/MrAmii/Matrix-CRT-vscode-theme" data-color-scheme="no-preference: dark; light: dark; dark: dark;" data-icon="octicon-star" data-size="large" aria-label="Star MrAmii/Matrix-CRT-vscode-theme on GitHub">Repository</a>

# After installation Guide

## Getting font, line numbers and terminal cursor blink

- Add the following to your settings.json

```json 
    "editor.lineNumbers": "relative", //Used for navigation with vim, otherwise replace relative with on

    "editor.fontFamily": "Fira Code, Cascadia Code, Consolas, Courier New, monospace",
    "editor.fontLigatures": true,
    "editor.fontWeight": "normal",
    "editor.fontSize": 12.5,
    "editor.lineHeight": 1.1,
    "editor.letterSpacing": 1, 
    "editor.cursorStyle": "line",
    "editor.cursorWidth": 2,
    "editor.cursorBlinking": "blink",
    "editor.renderWhitespace": "selection",
    "editor.renderControlCharacters": true,
    "editor.renderLineHighlight": "line",
    "editor.renderFinalNewline": "dimmed",

    "terminal.integrated.fontFamily": "Fira Code, Cascadia Code, Consolas, Courier New, monospace",
        "terminal.integrated.cursorBlinking": true
    }
```


 
- navigate there by entering "The Command Palette" by pressing Ctrl+Shift+p and typing settings and selecting Preferences: User settings(JSON), then paste the following block in respecting the structures already present.

#### You will be using this command often in the future, alternatively if  you click the drop down menu and press >
*Most fonts should be Fira Code and can be changed by editing the fontFamily*

## Create glowing text effect

- Navigate to the extension [Custom CSS and JS Loader](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css)
> **WARNING** Read the description and warnings of <u>Costume CSS and JS Loader</u> extension, use at your own risk.
- Create a directory (folder) named after the extension wherever you would like, I put mine within the Visual Studio Code folder in Documents.
- Create a new file in VSCode named custom.css and save it there.
- In the file paste the following.
- In the file paste the following.

```css
:root {
    --text-shadow-color: #00ff4034;
}

.monaco-editor .mtk {
    text-shadow: 0 0 2px var(--text-shadow-color), 0 0 4px var(--text-shadow-color), 0 0 6px var(--text-shadow-color);
}

* {
    text-shadow: 0 0 2px var(--text-shadow-color), 0 0 4px var(--text-shadow-color), 0 0 6px var(--text-shadow-color);
}

.monaco-editor .mtk.italic, .monaco-editor .mtki {
    text-shadow: 0 0 2px var(--text-shadow-color), 0 0 5px var(--text-shadow-color);
}

.monaco-editor .mtk.pasted {
    text-shadow: 0 0 5px var(--text-shadow-color), 0 0 10px var(--text-shadow-color), 0 0 15px var(--text-shadow-color);
}
```

- Save and then in the settings.json add
```json
    "vscode_custom_css.imports": [
        "file:///C:/Users/{YOURUSERNAME}/Documents/Visual Studio Code/Custom CSS and JS Loader/custom.css"
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
        "file:///C:/Users/{YOURUSERNAME}/Documents/Visual Studio Code/Custom CSS and JS Loader/custom.css"
        "file:///C:/Users/{YOURUSERNAME}/Documents/Visual Studio Code/Custom CSS and JS Loader/index.js"
    ],
```

 *Reload Custom CSS and JS, you should now have the cursor effect*

# *"Welcome to the real world" -Morpheus* #

