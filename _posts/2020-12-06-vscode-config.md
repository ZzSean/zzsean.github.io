---

layout:     post

title:      "Vscode"

subtitle:   " Configure for Vscode "

date:       2020-12-06 17:42:00

author:     "Zz"

header-img: "img/default-bg.jpeg"

catalog: true

tags:

    - vscode

---

vscode|

## Download

https://code.visualstudio.com

## Plugin

1. Vim: https://github.com/VSCodeVim/Vim
2. C/C++
3. GitLens
4. Python
5. Chinese (optional)

## Settings

```
{
    "files.trimTrailingWhitespace": true,
    "terminal.integrated.fontFamily": "Meslo LG M for Powerline",
    "C_Cpp.updateChannel": "Insiders",
    "editor.rulers": [
      80
    ],
    "editor.lineNumbers": "relative",
    "editor.defaultFormatter": "ms-vscode.cpptools",
    "editor.formatOnPaste": true,
    "editor.formatOnType": true,
    "editor.tabSize": 2,
    "editor.minimap.enabled": true,

    // vim
    "vim.easymotion": true,
    "vim.incsearch": true,
    "vim.useSystemClipboard": true,
    "vim.useCtrlKeys": true,
    "vim.hlsearch": true,
    "vim.insertModeKeyBindings": [
      {
        "before": ["j", "j"],
        "after": ["<Esc>"]
      }
    ],
    "vim.normalModeKeyBindingsNonRecursive": [
      {
        "before": ["<C-n>"],
        "commands": [":nohl"]
      },
      {
        "before": ["Z", "Z"],
        "commands": [
            ":wq"
        ]
      },
      {
        "before": ["L"],
        "after": ["$"]
      },
      {
        "before": ["H"],
        "after": ["^"]
      }
    ],
    "vim.visualModeKeyBindings": [
        //{
        //    "before": [
        //        ">"
        //    ],
        //    "commands": [
        //        "editor.action.indentLines"
        //    ]
        //},
        //{
        //    "before": [
        //        "<"
        //    ],
        //    "commands": [
        //        "editor.action.outdentLines"
        //    ]
        //},
    ],
    "vim.operatorPendingModeKeyBindings": [
        {
            "before": ["L"],
            "after": ["$"]
        },
        {
            "before": ["H"],
            "after": ["^"]
        }
    ],
    "vim.leader": "<space>",
    "vim.handleKeys": {
      "<C-a>": false,
      "<C-b>": false,
      "<C-d>": false,
      "<C-f>": false,
      "<C-y>": false
    },
}
```

## ShortCuts

For MacOS: <https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf>

For Windows: <https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf>

**Customized**

1. Focus on File Explorer: Shift + 1
2. Focus on Terminal: Shift + 2
3. Maximum terminal: Command + M(MacOS), Ctrl + F11(Windows)
4. Toggle terminal: Ctrl + `(Windows)
5. Toggle minimap: Shift + `

Tips: **_Command_** for VSCode, **_Ctrl_** for Vim. 














