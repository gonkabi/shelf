# Contents
<!--ts-->
   * [Contents](#contents)
   * [Setting](#setting)
   * [Operate](#operate)
      * [Insert clipboard without any completions](#insert-clipboard-without-any-completions)
      * [Activate backspace for insert mode](#activate-backspace-for-insert-mode)

<!-- Added by: shota, at: Wed Dec  2 11:07:22 JST 2020 -->

<!--te-->

# Setting

# Operate
## Insert clipboard without any completions
Use `:set paste`.  
If you wanna `:set nopaste` automatically after back to normal mode, add followings into your vimrc.

```
autocmd InsertLeave * set nopaste
```

## Activate backspace for insert mode
In some environment, need to add the following description to activate backspace for insert mode.  
```
set backspace=indent,eol,start
```
