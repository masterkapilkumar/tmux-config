# tmux-config
User friendly tmux configuration

set -g prefix C-a

unbind C-b

bind C-a send-prefix

bind r source-file ~/.tmux.conf \; display "Reloaded"

bind | split-window -h
bind - split-window -v

bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D

bind -r h resize-pane -L 5
bind -r j resize-pane -D 5
bind -r k resize-pane -U 5
bind -r l resize-pane -R 5

set -g base-index 1
setw -g pane-base-index 1

set -g default-terminal "screen-256color"

setw -g monitor-activity on
set -g visual-activity on

set -g pane-border-fg green
set -g pane-border-bg black
set -g pane-active-border-fg white
set -g pane-active-border-bg yellow

#set -g message-fg white
#set -g message-bg yellow
set -g message-attr bright


set -g status-left-length 52
set -g status-right-length 451
set -g status-fg white
set -g status-bg colour234
set -g window-status-activity-attr bold
set -g pane-border-fg colour245
set -g pane-active-border-fg colour39
set -g message-fg colour16
set -g message-bg colour221
set -g message-attr bold
set -g status-left '#[fg=colour235,bg=colour252,bold]  #S#[fg=colour252,bg=colour238,nobold]#[fg=colour245,bg=colour238,bold] #(whoami)#[fg=colour238,bg=colour234,nobold]'
set -g status-right '#[fg=colour39, bg=colour234]#[fg=colour234,bg=colour39]%A, %d %b %Y %I:%M %p'
set -g window-status-format "#[fg=white,bg=colour234] #I #W "
set -g window-status-current-format "#[fg=colour234,bg=colour39]#[fg=colour25,bg=colour39,noreverse,bold] #I  #W#[fg=colour39,bg=colour234,nobold]"

bind-key ` next-window
#bind-key ~ previous-window

#set-window-option -g automatic-rename on
set-option -g set-titles on

unbind C-t
bind -n C-t new-window
unbind C-w
bind -n C-w confirm-before -p "kill-pane #P? (y/n)" kill-pane

set-option -g status-position top
