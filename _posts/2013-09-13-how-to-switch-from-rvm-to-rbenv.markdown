---
layout: post
title: "How to switch from rvm to rbenv"
date: 2013-09-13 11:06
comments: true
categories: [ruby,rbenv,tutorial]
keywords: ruby,rbenv,tutorial,how,rvm
descripton: How to switch from RVM to Rbenv the easy way.
---

The first question you might ask yourself is *Why should/would I need to switch?*
The answer is simply *you don't.* It is completely up to you whether or not you want to. I've found that in my development workflow rbenv just works better. I don't have to worry about managing gemsets. *Bundler* takes care of all that for me already.

<!-- more --> 
##Remove RVM
````
  rvm implode
````

##Installing Homebrew
Install [Homebrew](http://www.brew.sh) if you don't already have it on your system. **Homebrew** acts as a package manager for OSX. It makes life just a little bit easier on us mac users. 

````
  ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"
````

###Configure Homebrew
Run the code below to make sure everything installed successfully. If it did you should get a message back saying *Your system is raring to brew*
````
  brew doctor
````

Next we needed to update.
````
  brew update
````

##Installing Rbenv
Homebrew makes it stupid simple to install rbenv.
````
  brew install rbenv
  brew install ruby-build 
````

##Configuring Rbenv
Next you will need to configure your terminal to load the correct path for rbenv. For my example I'm using [ZSH](https://github.com/robbyrussell/oh-my-zsh). If you haven't checked it out yet, you should because its awesome. I had to edit my ~/.zprofile like so.

````
  sublime ~/.zprofile
  export PATH="$HOME/.rbenv/bin:$PATH"
  eval "$(rbenv init -)"
````

*Note:* I'm using sublime as my text editor. Just substitute your editor for sublime to open up the file.
*Note:* If you are not using ZSH you might have to edit <code>~/.profile</code> or <code>~/.bash_profile</code> instead.


##Bonus: Using Rbenv
For my workflow I found Rbenv to just be a lot simpler than rvm. I hated having to manage gemsets and whatnot. I like simplicity.

###Installing Ruby
````
  rbenv install 2.0.0
````
Hit tab to autocomplete the ruby version so you get the latest and greatest.

Then don't forget to rehash after installing.
````
  rbenv rehash
````

###Useful Commands:
Sets the current directory to use that version of ruby.
````
 rbenv local 2.0.0
````

Sets the default version of ruby to be 2.0.0.
````
 rbenv global 2.0.0
````





