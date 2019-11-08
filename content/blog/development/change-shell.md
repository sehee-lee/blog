---
title: 'Change default shell script in Mac'
date: 2019-11-08 13:13:13
category: 'Development'
---

Sometimes you want to change default shell. Someone prefer <strong>bash</strong> and another person prefer <strong>zsh</strong>.
After Mac OS is updated to Catalina, default shell is changed to zsh.
That means, if you already setting your development environment as bash, some setting should changed for zsh or change default to base.
Fortunary, changing default shell is very easy in Mac OS.<br>

The command for changing default shell is
~~~bash
chsh -s "SHELL BINARY PATH"
~~~

If you want to change default shell to zsh, type this command.
~~~bash
chsh -s /bin/zsh
~~~

Change the default shell to bash, type this command.
~~~bash
chsh -s /bin/bash
~~~

After type above command, system require your password.
Changed default shell is applied when restart terminal. <br>

If you don't know installed shell, can check this command.
~~~bash
➜ cat /etc/shells
# List of acceptable shells for chpass(1).
# Ftpd will not allow users to connect who are not using
# one of these shells.

/bin/bash
/bin/csh
/bin/dash
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
~~~