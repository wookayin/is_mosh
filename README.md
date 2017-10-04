`is_mosh`
=========

Detects whether the current shell is running under mosh or not.

It even works in a shell running inside tmux sessions, attached from a mosh session.


Usage
-----

You can either source the script or execute it as a sub-shell.

```
if is_mosh; then
  echo 'running under mosh'
else
  echo 'It is not under mosh'
fi
```

Why have you made this?
-----------------------

`mosh` is cool, but doesn't support 24-bit true color.
I needed a way to detect and disable true color feature on mosh environments.


LICENSE
-------

MIT
