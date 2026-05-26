Color
=====

CLI utilities for choosing ANSI terminal colors:
* `color` is a self contained ruby script to choose colors and print the
  xterm 256 color table.
* `ecolor` is an Emacs's lisp script designed to run from the command line
  that is similar to `color` but uses Emacs's internal color routines. It
  will also take an Emacs color name as input.

Usage
-----

With no arguments, `color` will print a color table:

    $ color

Output:
![Screenshot of Colortable](./media/colortable.png?raw=true "Color Table Screenshot")

`color` can take input colors in the forms:
* `#rrggbb`
* `rrggbb`
* `#rgb`
* `rgb(r, g, b)`
* `r,g,b`

`ecolor` can take input color in [Emacs's form](https://www.gnu.org/software/emacs/manual/html_node/emacs/Colors.html):
* A name like `dark orange` or `medium sea green`
* `#rgb`
* `#rrggbb`
* `#rrrgggbbb`
* `#rrrrggggbbbb`

Examples:

    $ color '#ccffcc'
    #ccffcc rgb(204,255,204) -> 194: #ccffcc rgb(204,255,204) fg: \e[38;5;194m bg: \e[48;5;194m Sample Foreground Sample Background
    $ color 'rgb(100,200,0)'
    #64c800 rgb(100,200,  0) -> 112: #66cc00 rgb(102,204,  0) fg: \e[38;5;112m bg: \e[48;5;112m Sample Foreground Sample Background
    $ color ff3
    #ffff33 rgb(255,255, 51) -> 227: #ffff33 rgb(255,255, 51) fg: \e[38;5;227m bg: \e[48;5;227m Sample Foreground Sample Background
    $ ecolor salmon
    "salmon" (64250 32896 29298) #fa8072 -> ("color-209" 209 65535 34695 24415) 209: #ff875f rgb(255,135, 95) fg \e[38;5;209m bg: \e[48;5;209m Sample Foreground  Sample Background
    $ ecolor violet
    "violet" (61166 33410 61166) #ee82ee -> ("color-213" 213 65535 34695 65535) 213: #ff87ff rgb(255,135,255) fg \e[38;5;213m bg: \e[48;5;213m Sample Foreground  Sample Background
    $ ecolor turquoise
    "turquoise" (16448 57568 53456) #40e0d0 -> ("color-80" 80 24415 55255 55255) 80: #5fd7d7 rgb( 95,215,215) fg \e[38;5;80m bg: \e[48;5;80m Sample Foreground  Sample Background
    $ ecolor pink
    "pink" (65535 49344 52171) #ffc0cb -> ("color-218" 218 65535 44975 55255) 218: #ffafd7 rgb(255,175,215) fg \e[38;5;218m bg: \e[48;5;218m Sample Foreground  Sample Background

And how it looks on a terminal:
![Screenshot of CLI Examples](./media/samplecli.png?raw=true "CLI Examples")

Copyright and License
---------------------

Copyright © 2023-2026 David Caldwell <david@porkrind.org>

License: [GPLv3](./LICENSE.md)
