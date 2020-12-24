---

layout:     post

title:      "Latex in Vscode"

subtitle:   " Configure for latex Vscode "

date:       2020-12-15 17:42:00

author:     "Zz"

header-img: "img/default-bg.jpeg"

catalog: true

tags:

    - vscode

---

vscode|

## Plugin

1. LaTex Workshop

## Settings

```
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
```

## Forward Search

正向搜索指的是从 .tex源文件向编译生成的 PDF 文件的跳转。这部分我们主要需要寻找到合适的方式，在命令行状态打开 Skim 应用。

根据 Skim 官网的介绍 ，Skim 提供了名为 displayline的脚本，用于和 TeX 正反同步协同工作。其脚本位于

```
/Applications/Skim.app/Contents/SharedSupport/displayline
```

具体用法则是

```
/Applications/Skim.app/Contents/SharedSupport/displayline %line "%pdffile" "%texfile"
```

此处 `%line`表示` .tex`文件的行号， `%pdffile`表示编译生成的 PDF 文件的完整路径， `%texfile`则是对应的` .tex`源文件。考虑到我们对反向搜索也有需求，按照官方文档，我们还需要加上 `-r`参数。

## Backward Search

反向搜索中，我们需要让 Skim 能够打开 VSCode，并将文件名和相应的行号正确地传给 VSCode。根据 Skim 官网的介绍 ，它只会从 `/usr/bin`和 `/usr/local/bin`中检索可执行程序。为此，我们需要将 VSCode 的可执行程序软链到这两个目录中的一个当中.

```
ln -sf /Applications/Visual\ Studio\ Code.app/Contents/MacOS/Electron /usr/local/bin/vscode
```

至此，我们在命令行中执行 `vscode -g "%file":%line`即可打开 `%file`文件并定位到第 `%line`行。于是，我们只需要在 Skim 的同步配置中将预设改为「自定义」，并将命令和参数分别设置如下：

- Command: `vscode`
- Arguments: `-g "%file":%line`