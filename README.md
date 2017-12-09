# My dotfiles (WIP)

### How to [Fira Code](https://github.com/tonsky/FiraCode), [Operator Mono](https://www.typography.com/blog/introducing-operator) & [Atom One Dark theme](https://marketplace.visualstudio.com/items?itemName=akamud.vscode-theme-onedark) all together (on VScode)

Hello, currently VScode is a bit a pain in the ass to make a decent
 configuration for. Here is how to setup all 3 of them.

Beware ! This setup only works for all of the 3, some toggles are needed if
  want to use other themes.

Globally, the result will be like this.
![monokai operator](https://i.imgur.com/gxgwhQV.png)
![monokai operator second part](https://i.imgur.com/o5ujssa.png)

### Steps

If you're interested in, there are all the steps to make it work:
- Install _Operator Mono_ (paid) & _Fira Code_ (free) on your system.
- Install the **Custom CSS and JS** plugin.
- Reload it, then don't forget to enable the plugin by `F1` (or `ctrl+shift+P` if you've
  installed Sublime shortcuts) and click on !! **Enable Custom CSS and JS** !! (or it
  won't work...).
- Create a `vscode_styles.css` file that will contain your configuration, put if in some
  safe place like `~/Documents/`
- Copy this code inside:
```css
/* Target pretty all what starts with .mtk */
[class^='mtk'], .detected-link {
  font-family: 'Operator Mono Medium';
  font-style: italic;
}

/* Some stuff I want as regular style */
.mtk3,
.mtk8 {
  font-family: 'Operator Mono Medium';
  font-style: normal;
}

/* Ligatures */
.mtk6,
.mtk13,
.mtk15 {
  font-family: 'Fira Code';
  font-style: normal;
}

/* Underline */
.mtku {
  text-decoration: underline;
}
/* Italic */
.mtki {
  font-style: italic;
}
/* Bold */
.mtkb {
  font-weight: bold;
}

```
- Open the file in a browser to check **the absolute object path** to your file in the
  url, will be needed below.
- Add/update the following to the **User settings**, shortcut: `ctrl + ,`
```json
"workbench.colorTheme": "Atom One Dark",
"editor.fontFamily": "'Fira Code','Operator Mono Medium', 'Droid Sans Mono', 'monospace', monospace, 'Droid Sans Fallback'",
"editor.fontLigatures": true,
"editor.fontSize": 15,
"vscode_custom_css.imports": ["file:///home/yourself/Documents/your/vscode_styles.css"],
```
- Reset vsCode and :tada: ! :D

### Conclusion

One thing you need to know, is that each different theme have it's own way of writting
  the different tags. By that, I mean that my configuration works for this particular
  theme but won't work for, let's say [Monokai Operator](https://marketplace.visualstudio.com/items?itemName=markfknight.monokai-operator-theme).

  Indeed, some classes are not the same. Since [this](https://medium.com/@zamamohammed/multiple-fonts-alternative-to-operator-mono-in-vscode-7745b52120a0) method doesn't work anymore...you need to target the classes by
  yourself... Open your palette with `F1` and type in `Toggle Developer Tools`, you'll
  be able to see the class you need to change.

![specific class](https://i.imgur.com/46DMVvw.png)

Then feel free to toggle my `.css` to your taste !

As you can see, it's working but it's just not _really_ out-of-the-box friendly.