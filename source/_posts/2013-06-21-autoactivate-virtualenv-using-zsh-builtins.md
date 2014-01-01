---
layout: post
title: "Autoactivate virtualenv using zsh builtins"
location: "Kollam" 
description: ""
category: "hack"
tags: []
---
So I have been using virtualenv and virtualenvwrapper for managing python
packages.If you are moving around in your directory tree it realy gets annoying
if you have to activate the virtualenv everytime you openup a new tmuz pane or a 
terminal window.I have switched to zsh recently and just discovered a feature
to automate this.Just simply put this in your .zshrc.
{% highlight bash %}

function chpwd(){
emulate  zsh
if [ -e ".venv" ]; then
    # Check to see if already activated to avoid redundant activating
    if [ "$VIRTUAL_ENV" != "$VIRTUALENVWRAPPER_HOOK_DIR/`cat .venv`" ]; then
        _VENV_NAME=`cat .venv`
        echo Activating virtualenv $_VENV_NAME
        workon $_VENV_NAME
    fi
fi
}

{% endhighlight %}

You have to create a .venv file in your working directory with name
of the virtualenv in it  to make use of this.There are plenty of similar solutions even if you don't use zsh (which you should)


