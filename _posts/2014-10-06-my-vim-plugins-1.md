---
published: true
layout: post
title: "My Vim Plugins - 1"
author: Boy Sandy Gladies Arriezona
tags:
    - vim
    - plugin
comments: True
---

## Introduction

First thing first. What is Vim? As far as I can tell, Vim is an imitation of Vi. But **tldr** it is an improved version of Vi now. The last thing that I remember is Vim is not a word processor, it is an editor. You should find the difference yourself.

So, now I wanna show you all Vim plugins that I used. It’s not much but it really help me a lot when I code.

``` viml
" Color scheme
NeoBundle 'flazz/vim-colorschemes'
" Network oriented reading, writing, and browsing
NeoBundle 'eiginn/netrw'
" Elegant buffer explorer
NeoBundle 'fholgado/minibufexpl.vim'
" Text filtering and alignment
NeoBundle 'godlygeek/tabular'
" Syntax for LESS (dynamic CSS)
NeoBundle 'groenewege/vim-less'
" CSS3 syntax support
NeoBundle 'hail2u/vim-css3-syntax'
" Statusline/tabline for Vim
NeoBundle 'itchyny/lightline.vim'
" Distraction free
NeoBundle 'junegunn/goyo.vim'
" Vim motion on speed
NeoBundle 'Lokaltog/vim-easymotion'
" Python tag list
NeoBundle 'majutsushi/tagbar'
" Auto close scope (brackets, quotes, etc)
NeoBundle 'Raimondi/delimitMate'
" Awesome HAML to HTML by CTRL-E on HTML files
NeoBundle 'rstacruz/sparkup', {'rtp': 'vim/'}
" Awesome syntax checking plugin
NeoBundle 'scrooloose/syntastic'
" Snippet engine and snipet lists
NeoBundle 'honza/vim-snippets'
NeoBundle 'SirVer/ultisnips'
" Visualize your undo tree
NeoBundle 'sjl/gundo.vim'
" Unite, async and tags support
NeoBundle 'Shougo/neomru.vim'
NeoBundle 'Shougo/unite.vim'
NeoBundle 'Shougo/vimproc.vim', { 'build' : { 'unix' : 'make -f make_unix.mak', }, }
NeoBundle 'tsukkee/unite-tag'
" Expand visual selection by multiple 'v'
NeoBundle 'terryma/vim-expand-region'
" String substitute for singular / plural (context, sensitive)
NeoBundle 'tpope/vim-abolish'
" Language-agnostic commenting plugin
NeoBundle 'tpope/vim-commentary'
" Git integration
NeoBundle 'tpope/vim-fugitive'
" Enable repeating supported plugin
NeoBundle 'tpope/vim-repeat'
" Quoting/parenthesizing made simple
NeoBundle 'tpope/vim-surround'
" Awesome completion
NeoBundle 'Valloric/YouCompleteMe'
"Multiple cursor
NeoBundle 'terryma/vim-multiple-cursors'
```
