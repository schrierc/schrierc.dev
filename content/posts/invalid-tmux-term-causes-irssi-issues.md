+++
title = 'Invalid tmux term causes irssi issues'
date = 2011-07-26T17:29:00Z
tags = ["linux", "bash", "tmux"]
draft = false
+++

Today I finally switched my long-running IRC screen session to tmux. I rarely
disconnect so I was simply waiting for a "good" time.

After a few minutes I noticed that my irssi scrollback was misbehaving; only
half of my window would redraw when I pressed PgUp of PgDn.

I had manually set `TERM=xterm` in my bashrc; however, tmux advises only
using `screen` or `screen-256color` as the term. I have no idea why I had
specified term within my bashrc; removing the line and restarting tmux
corrected the issue.

http://tmux.cvs.sourceforge.net/viewvc/tmux/tmux/FAQ
