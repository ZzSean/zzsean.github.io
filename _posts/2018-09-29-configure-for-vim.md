---

layout:     post

title:      "Vim"

subtitle:   " Configure for Vim "

date:       2018-09-29 20:42:00

author:     "Zz"

header-img: "img/default-bg.jpeg"

catalog: false

tags:

    - code

---

vim|


## k-vim

**dev**

```
git clone https://github.com/wklken/k-vim.git
# mac
brew install ctags
brew install the_silver_searcher
# ubuntu
sudo apt-get install ctags
sudo apt-get install build-essential cmake python-dev  #编译YCM自动补全插件依赖
sudo apt-get install silversearcher-ag
# use python
sudo pip install flake8 yapf
```

**install**

```
cd k-vim/
sh -x install.sh
```

**uninstall**

```
cd ~ && rm -rf .vim .vimrc .vimrc.bundles && cd -
```

**tips**

1. YCM should be installed without the anaconda evn
2. Any other problems can be inferenced [k-vim](https://github.com/wklken/k-vim)









