# Tmux

## Purpose

Tmux allows you to keep running programs even when SSH gets disconnected. In addition, tmux also allows you to create "tabs" which makes it convenient to do multiple things at once, such as editing code and running a web server.

## Installing

Simply run `sudo pkg install tmux`

## Usage

It is easiest to always run `tmux a` in your jail and see if it attaches to a running session. If that fails, just run `tmux` once and subsequently use `tmux a` again.

All commands are prefixed by `Ctrl-b`, and here is an overview of several useful ones:

* `Ctrl-b c` (so press `Ctrl-b` and then just `c`) to create a new window. 
* `Ctrl-b n` switches to the next window.
* `Ctrl-b p` switches to the previous window.
* `Ctrl-b 1` switches to the first window.
* `Ctrl-b 2` switches to the second window.
* `Ctrl-b d` detaches from the current session.

## More Info

You can always check `man tmux` for more information.
