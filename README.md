`is_mosh`
=========

Detects whether the current shell is running under [mosh][mosh] or not.

It even works in a shell running inside tmux sessions, when attached from a mosh session.

> [!IMPORTANT]
> mosh 1.4+ now supports 24-bit color support (since October 2022) so you will probably no longer need this.
> This project is archived, but `is_mosh` would still work as designed.

Usage
-----

You can either source the script or execute it as a sub-shell.

```bash
if is_mosh; then
  echo 'running under mosh'
else
  echo 'It is not under mosh'
fi
```

Try `is_mosh -v` or `is_mosh --verbose` to see messages printed to stdout (`mosh` or `not mosh`).

NOTE: `pstree` and tmux 2.1+ are required ([#1][GH-1]).

Why did you make this?
-----------------------

`mosh` is awesome, but [didn't support 24-bit true color][mosh-961] until mosh 1.4.0.
I needed a way to detect and disable true color feature on mosh environments.
To see an example of vimrc to automatically turn on/off termguicolors, see my [vimrc][vimrc-example].
Please see [a stackexchange thread](https://unix.stackexchange.com/questions/395491/detect-whether-the-current-terminal-is-through-mosh-or-not) for the discussion.


LICENSE
-------

The MIT License (c) 2017-2020 Jongwook Choi (@wookayin)


[mosh]: https://mosh.org/
[mosh-961]: https://github.com/mobile-shell/mosh/issues/961
[vimrc-example]: https://github.com/wookayin/dotfiles/blob/0d44f9c24328ccba5e21cf776b33bdef912fbdc6/vim/vimrc#L579-L609
[GH-1]: https://github.com/wookayin/is_mosh/issues/1
