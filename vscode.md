
- [open a file in current vscode using terminal](https://stackoverflow.com/questions/41377489/how-to-open-a-file-from-the-integrated-terminal-in-visual-studio-code)

  ```code -r filename.js```

- [Switch Terminals in vscode-terminal](https://stackoverflow.com/questions/48440673/how-to-switch-between-terminals-in-visual-studio-code/64250667)

  ```
  Toggle between terminal and editor focus
      ctrl+`
  Move to previous terminal
      Ctrl+PageUp (macOS Cmd+Shift+])
  Move to next terminal
      Ctrl+PageDown (macOS Cmd+shift+[)
  ```


- [vscode not recognizing react code as react javascript instead it format it as vanilla javascript](https://stackoverflow.com/questions/54462519/why-vscode-is-not-recognizing-react-code-as-react-javascript-instead-it-format-i)

  I don't read anything about react in prettier documentation

  As far as I understand, react code should be put in .jsx files, not .js

  https://reactjs.org/docs/introducing-jsx.html

  > React doesn’t require using JSX, but most people find it helpful as a visual aid when working with UI inside the JavaScript code

  Also I did [this](https://www.reddit.com/r/vscode/comments/8h2vyt/auto_detect_language_mode_for_react_files/)

  You can use the "files.associations" option to make it so that all JS files are JavaScript React.

        "files.associations": {
            "*.jsx": "javascriptreact"
        }


- #### For situations that require adding focus-behaviour to label/div that has an input within it, instead of input [try using:focus-within](https://stackoverflow.com/questions/5978239/anyway-to-have-a-label-respond-to-focus-css)

- #### [Selecting block of code](https://stackoverflow.com/questions/44956653/selecting-block-of-code-in-visual-studio-code) in Visual Studio Code

  Use Alt + Shift + → to expand the selection between braces or tags.

  Use Alt + Shift + ← to shrink the selection between braces or tags.