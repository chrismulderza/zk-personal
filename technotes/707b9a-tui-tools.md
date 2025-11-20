---
id: "707b9a"
title: "TUI Tools"
type: "note"
tags: []
date: "2025-11-20"
---

# TUI Tools

## Standards

- Terminal Colour Standards 
  [link](https://github.com/termstandard/colors)

## Currently using

### Midnight Commander

- Colour (theme) customization. 
  [link](https://love-coding.pl/en/midnight-commander-mc-and-color-customization-in-linux/)

### TMUX

#### Useful configurations

```tmux.conf

# When you start tmux, start zsh
set-option -g default-shell /bin/zsh
set-option -g default-command /bin/zsh

# Focus on terminal events
set -g focus-events on

# Start window index from 1
set -g base-index 1

# Start the index of the pane from 1
setw -g pane-base-index 1

# | Divides the pane vertically by |
bind | split-window -h

# - Split a pane horizontally
bind - split-window -v

# Move pane
bind-key h select-pane -L
bind-key j select-pane -D
bind-key k select-pane -U
bind-key l select-pane -R
bind-key 1 select-pane -t 1
bind-key 2 select-pane -t 2
bind-key 3 select-pane -t 3
bind-key 4 select-pane -t 4
bind-key C-g display-panes

# Resize pane
bind -r C-h resize-pane -L 1
bind -r C-l resize-pane -R 1
bind -r C-j resize-pane -D 1
bind -r C-k resize-pane -U 1

# Use 256 color terminal
set -g default-terminal "screen-256color"

# Override terminal emulator setting
set -ga terminal-overrides ',xterm*:smcup@:rmcup@'
set -ga terminal-override ',rxvt-uni*:XT:Ms=\E]52;%p1%s;%p2%s\007'

# Clipboard synchronization
unbind -T copy-mode M-w
unbind -T copy-mode C-w
bind-key -T copy-mode M-w send -X copy-pipe "xsel -i -p && xsel -o -p | xsel -i -b"
bind-key -T copy-mode C-w send -X copy-pipe "xsel -i -p && xsel -o -p | xsel -i -b"
bind-key C-y run "xsel -o | tmux load-buffer - ; tmux paste-buffer"

# It shines like a screen when in copy mode
bind-key [ copy-mode \; display "(Copy mode)"
bind-key Escape copy-mode \; display "(Copy mode)"
set-option -g display-time 800
set-option -g message-style bg="colour63"
set-option -g message-style fg="white"

# Draw a helm-like man page
bind-key m command-prompt -p "man:" "split-window -v 'exec man %%'"
```


## Tools to investigate

- Yazi (means "duck") is a terminal file manager written in Rust, based on
  non-blocking async I/O. It aims to provide an efficient, user-friendly, and
  customizable file management experience. [link](https://github.com/sxyazi/yazi)

- Rmpc is a beautiful, modern and configurable terminal based Music Player
  Daemon client. It is heavily inspired by ncmpcpp and ranger/lf file managers.
  [link](https://github.com/mierak/rmpc/tree/master)

- Taskwarrior FZF integration.
  [link](https://github.com/tom-doerr/taskwarrior-fzf/tree/master)

- Floating scratch terminal in tmux.
  [link](https://blog.meain.io/2020/tmux-flating-scratch-terminal/)

- Creating a Tmux Keybinding for Pop-up Sessions 
  [link](https://madprofessorblog.org/articles/creating-a-tmux-keybinding-for-pop-up-sessions/)

- Popup menus to help with managing the #tmux environment.
  [link](https://github.com/jaclu/tmux-menus/tree/main)

- A lightweight floating window manager for tmux that allows you to create
  customizable popup sessions for different workflows.
  [link](https://github.com/Subbeh/tmux-tpad)

- FZF buku script 
  [link](https://github.com/DanielFGray/fzf-scripts/blob/master/fzbuku)

- Example of how to localise images in a Zettelkasten system. 
  [link](https://github.com/sirupsen/zk/blob/master/bin/zk-assets-localize)

