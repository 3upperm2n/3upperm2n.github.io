---
layout: post
title:  "Install vim plugins using vundle"
date:   2016-12-22 
categories: ["linux"]
---

Here is the Vundle tutorial on the [github](https://github.com/VundleVim/Vundle.vim).


Step 1 : download vundle to your ~/.vim folder

```bash
$git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

Step 2: edit your .vimrc to add plugins

```vim
set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

Plugin 'VundleVim/Vundle.vim'
Plugin 'Valloric/YouCompleteMe' 
Plugin 'SirVer/ultisnips'

call vundle#end()          
filetype plugin indent on 
```

Step 3 : download plugins 

* graphical approach

Launch vim and run :PluginInstall

* commandline approach

```bash
$vim +PluginInstall +qall
```

That's all!
