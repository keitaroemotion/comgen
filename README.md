# comgen

Comment generation auxiliary tool. It can dispatch the comment according to the entension of the target file or simply the shebang extension.

## Installation

To be honest there is no installation. The purpose of this script is in order to make it callable from vim macro.
Such that, the conceivable scenario is:


1. Copy the comgen file somewhere under the .vim directory:
```
$cp comgen ~/.vim/some.vim/scripts
```

2. Configure the vimrc file, for example

```
let script_dir  = "~/.vim/some.vim/scripts/"
:command! Komment   call Komment()
function! Komment()
    let result = system(g:script_dir . "comgen " . expand('%:p'))
    put =result
endfunction
```

Then all you need to do is to call the comgen script, with the absolute path of current buffer as an argument.
