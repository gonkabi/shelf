# Contents
<!--ts-->
   * [Contents](#contents)
   * [Setting](#setting)
      * [Change default editor](#change-default-editor)
      * [Set alias for git log](#set-alias-for-git-log)

<!-- Added by: shota, at: Wed Oct 21 14:19:05 JST 2020 -->

<!--te-->

# Setting
## Change default editor
Use `git config`.  
```
# Example: vim
git config --global core.editor vim
```

## Set alias for git log
"git lol" is the one of recommended alias for git log.  
You can set this alias as following.
```
git config --global alias.lol "log --graph --decorate --pretty=oneline --all --abbrev-commit"
```

