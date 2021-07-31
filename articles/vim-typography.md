# Vim Typography: Better Readability and Look

A few tricks to improve your Vim editor's readability and theming.
All examples are for editing ``.vimrc` and `.gvimrc` files.

`.gvimrc` is for GUI specific commands.
For instance, you should use it for things that you want to see in gVim or MacVim
and can't or don't want to use when Vim is running via terminal.

## GUI Specific:

### Theming (syntax highlighter)

    syntax enable
    set background=dark
    colorscheme themeName

Color schemes are stored in `.vim/colors` folder.

### Fonts

    set guifont=Droid\ Sans\ Mono\ 14
    "" or
    set guifont=DejaVu\ Sans\ Mono:h13

As you can see, when there are spaces in a font name, you have to use
`\` before them. There are also system differences when it comes to picking size.

This is an example of setup for many operating systems:

    if has("gui_gtk2")
      set guifont=Droid\ Sans\ Mono\ 13
    elseif has("gui_macvim")
      set guifont=Menlo\ Regular:h14
    elseif has("gui_win32")
      set guifont=Consolas:h11:cANSI
    endif

### Linespace (almost like line-height in CSS)

`linespace=4`

`Linespace` property doesn't work exactly like
`line-height` in CSS.
It sets the space between lines, not leading.

The default is 0. I like to use something around 4 or 5, it depends on
the font face.

## General:

### Terminal vs GUI

Things listed below don't look as well in a terminal as in a GUI rich editor
with a nice theme:

- error highlighting (ie: spellcheck),
- character limit line,
- current line highlight (not so bad but still worse than GUI apps).

Sometimes they work more like distractions than like handy hits.
Consider using some of them in `.gvimrc` instead of `.vimrc`.

### Characters per line limit

Set and show 80 characters limit.

    set textwidth=80
    set colorcolumn=+1

You'll see a line after 80th column.

### Line Numbers

    set number          " show line numbers
    set numberwidth=4   " width of number bar

### Text Highlighting

    set cursorline      " highlight current line
    set showmatch       " highlight matching <[{()}]>

### Autoindenting

    set autoindent      " set autoindenting on
    set copyindent      " copy the indentation from previous line


### Spell Check + Word Completion

    set spell spelllang=en_us
    set complete+=kspell

Press CTRL-N or CTRL-P in insert-mode to complete current word.

`2015-12-21`