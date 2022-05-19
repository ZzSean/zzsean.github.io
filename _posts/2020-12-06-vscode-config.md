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
2. C/C++：https://github.com/microsoft/vscode-cpptools
3. GitLens
4. Pytho, Pylance
5. Chinese (optional)
6. LaTex Workshop
7. Trailing Spaces
8. Viscose-cudacpp
9. Dark-plus-syntax

## Settings

```
{
  "files.trimTrailingWhitespace": true,
  "editor.fontFamily": "Monaco, Meslo LG S for Powerline",
  "terminal.integrated.fontFamily": "Meslo LG S for Powerline",
  "C_Cpp.updateChannel": "Insiders",
  "editor.rulers": [
    80
  ],
  "editor.lineNumbers": "relative",
  //"editor.defaultFormatter": "ms-vscode.cpptools",
  "editor.formatOnPaste": true,
  "editor.formatOnType": true,
  "editor.tabSize": 2,
  "editor.suggest.shareSuggestSelections": true,
  "editor.quickSuggestions": true,
  "workbench.editor.enablePreview": false,
  "editor.fontSize": 13,
  "editor.tokenColorCustomizations": {
    "textMateRules": [
      {
        "scope": [
          "comment"
        ],
        "settings": {
          "fontStyle": "italic"
        },
      },
    ]
  },
  // vim
  "vim.easymotion": true,
  "vim.incsearch": true,
  "vim.useSystemClipboard": true,
  "vim.useCtrlKeys": true,
  "vim.hlsearch": true,
  "vim.insertModeKeyBindings": [
    {
      "before": [
        "j",
        "j"
      ],
      "after": [
        "<Esc>"
      ]
    }
  ],
  "vim.normalModeKeyBindingsNonRecursive": [
    {
      "before": [
        "<C-n>"
      ],
      "commands": [
        ":nohl"
      ]
    },
    {
      "before": [
        "Z",
        "Z"
      ],
      "commands": [
        ":wq"
      ]
    },
    {
      "before": [
        "L"
      ],
      "after": [
        "$"
      ]
    },
    {
      "before": [
        "H"
      ],
      "after": [
        "^"
      ]
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
      "before": [
        "L"
      ],
      "after": [
        "$"
      ]
    },
    {
      "before": [
        "H"
      ],
      "after": [
        "^"
      ]
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
  // latex
  "latex-workshop.latex.tools": [
    {
      // 编译工具和命令
      "name": "xelatex",
      "command": "xelatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "-pdf",
        "%DOCFILE%"
      ]
    },
    {
      "name": "pdflatex",
      "command": "pdflatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOCFILE%"
      ]
    },
    {
      "name": "bibtex",
      "command": "bibtex",
      "args": [
        "%DOCFILE%"
      ]
    }
  ],
  "latex-workshop.latex.recipes": [
    {
      "name": "xelatex",
      "tools": [
        "xelatex"
      ],
    },
    {
      "name": "pdflatex",
      "tools": [
        "pdflatex"
      ]
    },
    {
      "name": "xe->bib->xe->xe",
      "tools": [
        "xelatex",
        "bibtex",
        "xelatex",
        "xelatex"
      ]
    },
    {
      "name": "pdf->bib->pdf->pdf",
      "tools": [
        "pdflatex",
        "bibtex",
        "pdflatex",
        "pdflatex"
      ]
    }
  ],
  "latex-workshop.latex.autoBuild.run": "never",
  "latex-workshop.latex.autoClean.run": "onBuilt",
  "latex-workshop.latex.clean.fileTypes": [
    "*.aux",
    "*.bbl",
    "*.blg",
    "*.idx",
    "*.ind",
    "*.lof",
    "*.lot",
    "*.out",
    "*.toc",
    "*.acn",
    "*.acr",
    "*.alg",
    "*.glg",
    "*.glo",
    "*.gls",
    "*.ist",
    "*.fls",
    "*.log",
    "*.fdb_latexmk",
  ],
  "latex-workshop.view.pdf.viewer": "external",
  "latex-workshop.view.pdf.external.synctex.command": "/Applications/Skim.app/Contents/SharedSupport/displayline",
  "latex-workshop.view.pdf.external.synctex.args": [
    "-r",
    "%LINE%",
    "%PDF%",
    "%TEX%"
  ],
  "latex-workshop.view.pdf.external.viewer.command": "/Applications/Skim.app/Contents/SharedSupport/displayline",
  "latex-workshop.view.pdf.external.viewer.args": [
    "0",
    "%PDF%",
  ],
  "workbench.iconTheme": "material-icon-theme",
  "workbench.colorTheme": "dark-plus-syntax",
  "workbench.editorAssociations": [
    {
      "viewType": "jupyter.notebook.ipynb",
      "filenamePattern": "*.ipynb"
    }
  ],
}
```

## ShortCuts

For MacOS: <https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf>

For Windows: <https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf>

**Customized**

1. Focus on File Explorer: Alt + Shift + E
2. Focus on Terminal: Ctrl/Command + `
3. Maximum terminal: Command + M(MacOS), Ctrl + F11(Windows)
4. Toggle terminal: Ctrl/Command + `/J
5. Toggle minimap: Alt/Command + Shift + A
6. Toggle Vim: Shift + Alt/Command + i
7. Toggle ActivityBar: Alt/Option + Ctrl/Command + A

Tips: **_Command_** for VSCode, **_Ctrl_** for Vim. 

## Tips

In MacOS, long press jk cannot move the cursor, type this command in terminal and reboot VSCode

`defaults write com.microsoft.VSCode ApplePressAndHoldEnabled -bool false`













