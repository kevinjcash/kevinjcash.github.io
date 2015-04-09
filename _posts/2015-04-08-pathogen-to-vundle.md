---
layout: post
title: Moving From Pathogen To Vundle
date: 2015-04-08 20:00:00
---
I've been using Tim Pope's excellent
[Pathogen](https://github.com/tpope/vim-pathogen "Pathogen") for years now, and
I've loved it's simplicity. Cloning a git repository is easy, and github is
where I tend to discover plugins anyway. But as I continued to incorporate more
and more plugins, I started running into growing pains. I use vim on a few
different computers, and sometimes I need to set up vim in a virtual machine or
something. I have my vimrc tracked in github, but the set of plugins I was using
wasn't tracked in there.

I dabbled with setting up all my plugins as git submodules of my dotfiles repo,
which worked, but editing a gitsubmodules file and syncing the submodules is a
lot more work than just cloning a repo. It also meant I was configuring my vim
plugins in a totally different place than the rest of my vim settings. I wanted
something that would be tracked in git, but was still part of my vim
configuration.

Enter [Vundle](https://github.com/gmarik/Vundle.vim "Vundle").

Vundle is simple to use, and all configuration lives in my vimrc. Plugins are installed
and updated through commands in vim.  This means that my process for getting vim set up on
a new computer is this:

1. Install vim
2. Clone and symlink my vimrc
3. Clone vundle
4. Kick off vundle installation

Vim is probably already installed, and I already have a script that links my vimrc to
~/.vimrc.  I can add steps 3 and 4 to that script, giving me the holy grail: a one button
vim environment.

Well, almost. Some of the plugins that I use,
[Command-t](https://github.com/wincent/Command-T) for example, require a little additional
configuration. There's no reason I couldn't script that too though.

The other really nice benefit is that syncing my set up between computers is as easy as
pulling updates to my vimrc and running vundle's update and clean commands.
