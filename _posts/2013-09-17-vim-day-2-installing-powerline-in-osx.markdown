---
layout: post
title: "Vim: Day 2 - Installing Powerline in OSX"
date: 2013-09-17 09:31
comments: true
categories: ["vim,tutorials,customization"] 
keywords: vim,how,to,powerbar,osx,
descripton: How to install Powerline in OSX. The easy way.
---
I've been lurking on reddit for sometime checking out the sweet developer setups they have posted in some of their customization subreddits. They make me jealous a bit. So I set out to try to customize my own system with some of these things.

The thing I found in common with most of these setups were that the people were using *VIM.* Ok Check, I've got that installed. Now what? *Tmux.* Ok, thats pretty easy as well (Thanks homebrew!).

What I really had wanted is [Powerline](https://github.com/Lokaltog/powerline).Its a beautiful statusplugin for Vim that just makes it look *Sweet*. However I had some trouble getting it installed. I spent a lot of time trying to just get powerline installed. For some reason it wasn't installing into my correct directory and I couldn't find it anywhere once I had compiled it. But then I stumbled on a website that helped me get going. So Kudos to *saulict*. Here is his site. [How to Install Vim and Powerline in osx](http://saulic.info/blog/vim-powerline-mac-osx-howto/).

I'm writing this to hopefully help anyone else having issues with installation and for myself in the future. The instructions I'm going to post come mainly from his website there. But this is what worked flawlessly for me.

##Install the lastest version of VIM.
You need to make sure you have homebrew installed. after that you can run this command.
<code>brew install vim --with-python --with-ruby --with-perl</code>

##Install Vundle
This is what ended up working for me. With everything I tried before, I kept running into issues. [Vundle](https://github.com/gmarik/vundle) is **Awesome**. **Note:** The instructions below to install Vundle come directly from their github. 

1. <code>$ git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle</code>
2. Configure Bundles (Post this in your <code>~/.vimrc</code> file.

````
set nocompatible               " be iMproved
 filetype off                   " required!

 set rtp+=~/.vim/bundle/vundle/
 call vundle#rc()

 " let Vundle manage Vundle
 " required! 
 Bundle 'gmarik/vundle'

 " My Bundles here:
 "
 " original repos on github
 Bundle 'tpope/vim-fugitive'
 Bundle 'Lokaltog/vim-easymotion'
 Bundle 'rstacruz/sparkup', {'rtp': 'vim/'}
 Bundle 'tpope/vim-rails.git'
 " vim-scripts repos
 Bundle 'L9'
 Bundle 'FuzzyFinder'
 " non github repos
 Bundle 'git://git.wincent.com/command-t.git'
 " git repos on your local machine (ie. when working on your own plugin)
 Bundle 'file:///Users/gmarik/path/to/plugin'
 " ...

 filetype plugin indent on     " required!
 "
 " Brief help
 " :BundleList          - list configured bundles
 " :BundleInstall(!)    - install(update) bundles
 " :BundleSearch(!) foo - search(or refresh cache first) for foo
 " :BundleClean(!)      - confirm(or auto-approve) removal of unused bundles
 "
 " see :h vundle for more details or wiki for FAQ
 " NOTE: comments after Bundle command are not allowed...
````

3. Launch Vim and run <code>:BundleInstall</code>

##Configuring Powerline
If everything went well, you should have your powerline showing up in Vim now. I put these settings in my <code>.vimrc</code> I got from *saulict*. For me, its the little things that count. And I like the way this looked. 

````
syntax on
set background=dark
let g:Powerline_symbols = 'unicode'
set laststatus=2
set encoding=utf-8
set t_Co=256
set fillchars+=stl:\ ,stlnc:\
````

##Fixing Patched Fonts
The last step we need to do is install some patched fonts that will work with Powerline. 
<code>git clone https://github.com/Lokaltog/powerline-fonts.git</code>
You can install all these fonts if you wish or just pick and choose which ones you want to use. The one I am currently using is **Meslo**.

Once you have the fonts installed you need to open up **iTerm2**. 
Go to *Preferences > Profiles > Text*. Then you can select the font. My settings are <code>12pt Meslo LG L DZ Regular for Powerline<code>.
 I find that 12pt font works best for me on my 13" screen.

Once you set the font, go ahead and give your iTerm2 a restart and when you go to Vim you should have a nice looking Powerline waiting for you! Let me know if you have any issues, I'd be glad to try to help.


