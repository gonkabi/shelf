# Contents
<!--ts-->
   * [Contents](#contents)
   * [Setting](#setting)
   * [Operate](#operate)
      * [Insert clipboard without any completions](#insert-clipboard-without-any-completions)

<!-- Added by: shota, at: Fri Sep 18 16:54:13 JST 2020 -->

<!--te-->

# Setting

# Operate
## Insert clipboard without any completions
Use `:set paste`.  
If you wanna `:set nopaste` automatically after back to normal mode, add followings into your vimrc.

```
autocmd InsertLeave * set nopaste
```
