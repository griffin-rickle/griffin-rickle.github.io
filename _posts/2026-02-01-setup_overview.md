---
title: Welcome! AKA an overshare about my preferred development toolset
date: 2026-02-01
layout: default
---

# Welcome!
This is the first real post on my blog. Welcome!

## An Overshare about my preferred setup
I admit I was really excited to make my own blog site. Now that I've made one I'm forced to acknowledge the fact that I need to write about things now. So I will write about my preferred development toolset, and why it works for me.

### Preference Overview
Here is a short overview of my preferences, so we may delve into the why later:
- OS: [Fedora](https://fedoraproject.org/) (Personal), [RHEL](https://www.redhat.com) (Professional)
- Terminal Emulator: [alacritty](https://github.com/alacritty/alacritty)
- Terminal Multiplexer: [tmux](https://github.com/tmux/tmux/wiki)
- Shell: [bash](https://www.gnu.org/software/bash/)
- Text Editor: [NeoVim](https://github.com/neovim/neovim)
- SDK Manager: [asdf-vm](https://asdf-vm.com/)
- Environment Manager: [direnv](https://direnv.net/)

## Preferred OS - Fedora, RHEL
### The Journey
The first real Linux experience I had came from dual-booting Ubuntu with Windows in college. That turned into wiping Windows from my HDD and full-time booting Linux Mint on my HP Elitebook 8440p. My first professional experience came in 2016 when I got my first job slinging Java. I was back to Ubuntu, and I was determined to use SublimeText as my text editor and Gradle as my build tool and Java interface. I really leaned into the command line at the next job I got. The product was RHEL-based, so development was done on RHEL systems. Some folks even used Fedora because at that point the two were so similar. I was still using SublimeText as my text editor, but I was determined to get to a position where I could really fly on the command line.

After that job, I moved to a position where developers were provisioned fancy, flashy Macbooks. To someone who learned command line on RHEL systems, I felt like a fish out of water in iTerm. Pair that with the fact that I was forced to do work in Eclipse because our product was built on the OSGi framework, and you've got a situation that had me squirming after a year. Even at my current job, the first computer was also a Macbook. The development, staging, and production environments are all Linux, though, so I was managing just fine. Then, after 3 years with a Macbook, I was eligible for a new computer!

### Home Sweet Home
Finally, I was up for a laptop refresh and I was able to finagle myself a RHEL machine! How lovely that homecoming was. In the meantime I had been messing around with Fedora on my personal machines, and  I found that it just clicked because of all the practice I had at work. All of that stuff I had been doing on the side was really paying off, and opening up the command line on the new RHEL machine I was provisioned was like taking a breath of fresh air!

Overall I just find that if I'm deploying software on a linux server, I want to be doing development on a linux machine. And let's face it: who is deploying things on anything but Linux servers these days?

## Preferred Terminal Emulator: Alacritty
Honestly I think I just got really sick of iTerm on my Macbook and opted for something else. That something else turned out to be [Hyper](https://hyper.is/), the terminal built on Electron. There were some issues that reared their head with the interplay of Hyper, tmux, and copying text. It turned out to be pretty annoying. I also remember some issues with speed. Being built upon electron seemed to really drag it down. After that I was itching for something else which provided customizability but was a native app. That something turned out to be Alacritty. I enjoy the color palettes, fonts, and other customizations I can tinker with. I haven't looked back since!

### Possible Alternatives
There was certainly a ton of hype around [Ghostty](https://github.com/ghostty-org/ghostty) before and just after it came out. It kind of faded into the background after a while, though. I have heard really nice things about [kitty](https://github.com/kovidgoyal/kitty) and [wezterm](https://wezterm.org/index.html), which both offer the ability to view images without leaving the CLI. This is something I would really like about Alacritty but I haven't been bothered enough to actually make the switch.

## Preferred Terminal Multiplexer: tmux
There's not really much to say here, other than tmux allows me to create a new window when I navigate to a new project. I can make a quick vertical split, issue a quick command, then close the split. I can press `Ctrl+]` to navigate a split as a buffer, then press `v` or `Shift+V` to highlight text, then `y` to yank it into the clipboard. It's quite handy, and it's provided all of the stability, functionality, and customizability I need for my day to day.

### Possible Alternatives
I've heard that [Zellij](https://github.com/zellij-org/zellij) is "like tmux on steroids", but just like the situation with Alacritty, I've just never been bothered enough to give it a shot. I suppose I can also just use the tools native to Alacritty like splits or tabs. But I like where I am now. 


## Preferred Shell: bash
Ahh, bash. Good old bash. The world of software stands atop rickety poles and jerry-rigged scaffolds on top of a base foundation... of bash. We all know it. You can do anything with bash. Define your data pipelines, string up your CI/CD, manage your deployments, do whatever you want really! And you have no reason to worry if you're going to be within the realm of Unix; it's preinstalled and the default shell. You might run into some weird edge-cases when running your Unix sripts on a Posix machine (ahem), but those can _mostly_ be worked around. I have a hard time being bothered to use anything else.

### Possible Alternatives
What haven't we heard about here? [zsh](https://www.zsh.org/) and [fish](https://fishshell.com/) are probably the most popular alternatives (and isn't zsh the default on Macbooks these days?) AND fish has the upside of a successful (and public) [rewrite from C++ to Rust](https://fishshell.com/blog/rustport/). I'm probably more likely to try fish than zsh on that fact alone.

## Preferred Text Editor: NeoVim
Oh yeah, now we're getting to the good parts. I love NeoVim. I started with SublimeText, then as I got more familiar with the command line I started picking up a bit of Vim. Things progressed, and I started spending more time in the terminal and less time in other programs. I even felt the pain of having to reach over and use my mouse. What a pain! I just want to use the terminal and TUIs. What's so wrong about that? So I started using Vim more. I got a really cool Vim runtime set up. I had my list of vim plugins. And then I wrote my own vim plugin in python; something that lets me open a SPARQL file, execute it against a Stardog instance, and open a new split with the results formatted in Markdown. It actually worked pretty well. But it needed Vim to be compiled with python3 support, and it required a specific version of python3 to be installed on the host machine. It was pretty annoying in all honesty. So I switched to NeoVim, [swapped my init.vim for init.lua](https://github.com/griffin-rickle/neovim-configs), and never looked back.

Seriously, I love this editor. I use vim on deployment servers and the keybinds are all familiar because of my NeoVim usage. It can be as heavy or lightweight as I want it to be. I prefer a fully featured text editing experience and don't mind a few extra milliseconds of startup time. Especially if that startup time comes with the added benefit of LSP support for any project written in the languages I work most often with (Java, Javascript, Python). _Especially_ especially if I can debug those projects with a single keystroke, and manage those debug configurations easily from machine to machine. I digress. I really enjoy it, though I understand that NeoVim specifically as well as modal text editors in general are just not everyones cup of tea.

### Possible Alternatives
[Emacs](https://www.gnu.org/software/emacs/)? It does seem to be the endgame for folks who are passionate about their tools and general developer experience. I'm still in love with NeoVim though. Maybe once something rubs me wrong _enough_ the wrong way I'll get the urge.

## Preferred SDK Manager: asdf-vm
Catchy name aside, asdf-vm is a really well thought out piece of software. I used to manage all of the individual runtimes of all the languages I use myself, but dear lord this got to be so annoying. I don't really primarily work in one language. My everyday might involve looking at one or more codebases written in: Python, Javascript, Typescript, Java, and Ruby. Separately, I could install `pyenv`, `nvm`, `sdkman`, and `rbenv`. Or I could install asdf-vm and manage everything through that. I'll take the latter. Oh, and it comes with the bonus that it puts a single file at the root of any directory I want to use non-default sdk versions. Count me in!

### Possible Alternatives
I've heard that asdf-vm is the first step towards [Nix/NixOS](https://nixos.org/), but I've heard enough nightmares about the declarative language used to configure the OS. I'll stick with asdf until I'm feeling ready to tackle some of those crazy frustrating situations.

## Preferred Environment Manager: direnv
I don't know if I have a ton to say about `direnv` other than I really like when I `cd` to the root of a python project and my virtual environment is automatically activated. Plus my work involves a lot of Bash scripts which use environment variables which default to production values. It's really nice to be able to set my own environment variables at the root and not have to prefix the command with a long string of `THIS_DIR=/this/dir THAT_DIR=/that/dir`.

### Possible Alternatives
I think Nix might take care of this as well!

## How it all works together

Take an example: I have been assigned a bug in our bug tracking software. The bug appears in an app with a Javascript frontend and node/express back end, which reads from a graph database. The data in the graph database is populated via a Python library developed in house. 

I open two tmux windows and navigate to the node codebase in both of them. In one, I can start a debug session of the back-end server. In the other I can attach to the webpack development server so I can debug the front end. 

Actually now I am running the app, but my database isn't started -- a quick tmux split to start that up in a podman container. 

If the data seems to be malformed, I can navigate to the python library which loads the data into the database. My python env is automatically activated by direnv. The python binary was set up by asdf-vm and is also set automatically when I enter the directory. I can debug the entire importing process from NeoVim. 

This is how my setup enables me to easily navigate, debug, and diagnose issues across our entire architecture.

# Final Words
It was truly a feat making it this far! I hope that I didn't bore you but this is my site so... deal with it, I guess? Thanks for reading my stories about each of the tools I use, why I use them, and how it enables me to read and write multiple codebases and debug issues which happen across our entire architecture. 
