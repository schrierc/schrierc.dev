+++
title = 'tmux Repeating Keys'
date = 2011-07-28T14:41:00Z
draft = true
tags = ['linux', 'tmux']
+++

When upgrading from tmux 1.1 to 1.5 I found a few key bindings changed slightly.
In particular, the arrow keys used to switch panes now repeat.

I often use the sequence `C-b Down` immediately followed by Up and then Enter to
re-run a unit test. With 1.5 I was doing this too quickly (tmux's repeat-time is
500ms by default) so I was switched back to my previous pane. To fix this I
simply added the arrow keys to my .tmux.conf without the -r option:

```
bind-key Up select-pane -U
bind-key Down select-pane -D
bind-key Left select-pane -L
bind-key Right select-pane -R
```
