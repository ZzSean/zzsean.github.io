---

layout:     post

title:      "Sublime text3"

subtitle:   " 注册码及配置 "

date:       2018-05-07 20:42:00

author:     "Zz"

header-img: "img/default-bg.jpeg"

catalog: false

tags:

    - python

---

Sublime Text3注册码及配置|

**激活**

只需要把下面的字段加入到你的hosts文件即可：

```
0.0.0.0 www.sublimetext.com

0.0.0.0 license.sublimehq.com
```


Valild Keys

----- BEGIN LICENSE -----
sgbteam
Single User License
EA7E-1153259
8891CBB9 F1513E4F 1A3405C1 A865D53F
115F202E 7B91AB2D 0D2A40ED 352B269B
76E84F0B CD69BFC7 59F2DFEF E267328F
215652A3 E88F9D8F 4C38E3BA 5B2DAAE4
969624E7 DC9CD4D5 717FB40C 1B9738CF
20B3C4F1 E917B5B3 87C38D9C ACCE7DD8
5F7EF854 86B9743C FADC04AA FB0DA5C0
F913BE58 42FEA319 F954EFDD AE881E0B
------ END LICENSE ------



**配置**

Pacage control -> Install Package

A File Icon

Alignment

AutoFileName

BracketHighlighter

Colorsublime

Docblockr

Git

GitGutter

Markdown Preview

Markdown Editing

Material Theme

Side Bar

ConvertToUTF8

Python PEP8 Autoformat

SublimeCodeIntel

SublimeREPL

SublimeTmpl

```
"attr": {
        "author": "Sean Zz",
        "email": "zhangzheng123@sjtu.edu.cn",
        "link": "http://zzsean.github.io"
    }
```

Latextools

```
// Change the scope selectors to preview math
    // E.g. set it to "text.tex.latex meta.environment.math.block.be"
    // to only preview math environment
    // Set it to "text.tex.latex meta.environment.math"
    // to preview every math command or environment
    "preview_math_scope": "text.tex.latex meta.environment.math",

"windows": {
        // Path used when invoking tex & friends; "" is fine for MiKTeX
        // For TeXlive 2011 (or other years) use
        // "texpath" : "C:\\texlive\\2011\\bin\\win32;$PATH",
        "texpath" : "D:\\TOOLS\\CTEX\\MiKTeX\\miktex\\bin;$PATH;D:\\TOOLS\\ImageMagick-7.0.8-Q16",
        // TeX distro: "miktex" or "texlive"
        "distro" : "miktex",
        // Command to invoke Sumatra. If blank, "SumatraPDF.exe" is used (it has to be on your PATH)
        "sumatra": "D:\\TOOLS\\SumatraPDF\\SumatraPDF.exe",
        // Command to invoke Sublime Text. Used if the keep_focus toggle is true.
        // If blank, "subl.exe" or "sublime_text.exe" will be used.
        "sublime_executable": "",
        // how long (in seconds) to wait after the jump_to_pdf command completes
        // before switching focus back to Sublime Text. This may need to be
        // adjusted depending on your machine and configuration.
        "keep_focus_delay": 0.5
    },

```

Boxy theme

**Key bindings**

```
[
    
    {"keys": ["alt+m"], "command": "markdown_preview", "args": { "target": "browser"}},

    {"keys":["f1"],
    "caption": "SublimeREPL: Python - RUN current file",
    "command": "run_existing_window_command", "args":
    {"id": "repl_python_run",
    "file": "config/Python/Main.sublime-menu"}}

]
```




