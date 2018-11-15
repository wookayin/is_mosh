`is_mosh`
=========

Detects whether the current shell is running under [mosh][mosh] or not.

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

Try `is_mosh -v` or `is_mosh --verbose` for printing something (only in case it is mosh).


Why have you made this?
-----------------------

`mosh` is cool, but doesn't support 24-bit true color.
I needed a way to detect and disable true color feature on mosh environments.
Please see [a stackexchange thread](https://unix.stackexchange.com/questions/395491/detect-whether-the-current-terminal-is-through-mosh-or-not) for the discussion.


LICENSE
-------

MIT


[mosh]: https://mosh.org/
