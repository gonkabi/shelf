# Contents
<!--ts-->
   * [Contents](#contents)
   * [Setting](#setting)
      * [Change default editor](#change-default-editor)
      * [Set alias for git log](#set-alias-for-git-log)
      * [Color setting](#color-setting)
   * [Assist Tool](#assist-tool)
      * [gh-md-toc](#gh-md-toc)
      * [gitignore.io](#gitignoreio)

<!-- Added by: shota, at: Fri Dec  4 16:55:19 JST 2020 -->

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
## Color setting
Change color setting black and white into color.  
```
git config --global color.ui true
```

# Assist Tool
## gh-md-toc
gh-md-toc is for you if you want to generate TOC for README.md or GitHub's wiki page and don't want to install any additional software.  
https://github.com/ekalinin/github-markdown-toc  

## gitignore.io
Create useful .gitignore files for your project.  
https://www.toptal.com/developers/gitignore  

