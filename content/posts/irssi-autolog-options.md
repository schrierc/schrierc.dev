+++
title = "irssi autolog options"
date = 2011-06-24T16:41:00Z
tags = ["irc", "irssi"]
+++

My favorite IRC client is irssi. I keep a log of my conversations using autolog;
however, I dislike logs from chanserv, nickserv, and other random bots which
I'll never reference. I discovered that autolog has a setting to ignore them:

`/set autolog_ignore_targets chanserv nickserv`

While searching I also found `log_create_mode`; irssi's default file mode is
0644. I prefer to keep my conversations private unless I specifically broaden
permissions:

`/set log_create_mode 0600`

Now new messages and channels are private until I chmod them. 
