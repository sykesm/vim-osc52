# vim-osc52

This is yet another packaging of the Chromium hterm code that sends OSC 52
escape sequences to populate the terminal clipboard. There's nothing
particularly special about this copy except for a new function that sends all
yanked text to the terminal auto-magically. ¯\_(ツ)_/¯

## Installation

Use your favorite plugin manager to install it. I use [junegunn/vim-plug].

```viml
Plug 'sykesm/vim-osc52'
```

## Usage

If you want yank to send text to the terminal as well as the buffer, the
following mappings can be used:

```viml
if !has("gui_running") && !empty($SSH_CLIENT)
  nnoremap <silent> yy :<C-U>call YankToTerminalClipboard('yy')<CR>
  nnoremap <silent> y :set operatorfunc=YankToTerminalClipboard<CR>g@
  vnoremap <silent> y :<C-U>call YankToTerminalClipboard(visualmode(), 1)<CR>
endif
```

## License

This is covered by the original BSD-style license from Chromium. It can be
found in [LICENSE].

[junegunn/vim-plug]: https://github.com/junegunn/vim-plug
[LICENSE]: LICENSE
