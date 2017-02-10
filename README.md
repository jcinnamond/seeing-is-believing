# Seeing is believing emacs minor mode #

[Seeing Is Believing](https://github.com/JoshCheek/seeing_is_believing)
is a ruby gem to evaluate Ruby code, recording the results of each
line. This minor mode provides an easy way to run it from emacs on the
current region or entire buffer.

## Installation ##

Download the package and add it to your load path.

To install from [MELPA](https://melpa.org/), follow the [instructions in the MELPA readme](https://github.com/melpa/melpa#usage).

Once that's set up, you can run `(package-install 'seeing-is-believing)`

Alternatively, if you use [spacemacs](http://spacemacs.org/), add `seeing-is-believing` to your `dotspacemacs-additional-packages` variable in your `.spacemacs` file and reload your config.

## Using the package ##

Enable the mode by typing `M-x seeing-is-believing` or by adding
something similar to the following to your emacs init file:

```
(require 'seeing-is-believing)
(add-hook 'ruby-mode-hook 'seeing-is-believing)
```

When the mode is active you can run seeing is believing by typing `C-c
? s`. If you prefer the
[xmpfilter](https://rubygems.org/gems/rcodetools/versions/0.8.5.0)
style of explicitly specifying where you want to see the output type
`C-c ? x`. You can clear out the output from seeing is believing by
typing `C-c ? c`.

You can change the keybinding shortcuts from the default of `C-c ?` by
customising the `seeing-is-believing-prefix` variable
(`M-x set-variable <return> seeing-is-believing-prefix <return>`).

You can also customize or set variables that affect how `seeing-is-believing`
operates:

- `seeing-is-believing-executable` can be set to the name of the program file
  for the executable (default "seeing\_is\_believing")
- `seeing-is-believing-max-length` can be set to an integer that limits the
  length of lines produced, source plus comments (default 1000).
- `seeing-is-believing-max-results` can be set to an integer that limits the
  number of results produced, when `seeing-is-believing` shows multiple results
  per comment (default 10),
- `seeing-is-believing-timout` can be set to a decimal number for the number of
  seconds `seeing-is-believing` runs before it times out or to 0 for no timeout
  (default 0), and
- `seeing-is-believing-alignment` can be set to one of `'chunk`, `'file`, or
  `'line` to change the way `seeing-is-believing` aligns its comments, on a
  chunk-by-chunk basis, across the whole file, or on a line-by-line basis,
  effectively no alignment (default "chunk").

Either use the customize interface to set these, or set them in your `init.el`
file:

```lisp
(setq seeing-is-believing-max-length 150
      seeing-is-believing-max-results 10
      seeing-is-believing-timeout 10.5
      seeing-is-believing-alignment 'file)
```

## Licence ##

Copyright 2015 John Cinnamond

This mode is distributed under the same licence as GNU Emacs.

GNU Emacs is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 3, or (at your option)
any later version.

GNU Emacs is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with GNU Emacs; see the file COPYING.  If not, write to the
Free Software Foundation, Inc., 51 Franklin Street, Fifth Floor,
Boston, MA 02110-1301, USA.
