# Contents
<!--ts-->
   * [Contents](#contents)
   * [Setting](#setting)
      * [Change default editor](#change-default-editor)
      * [Set alias for git log](#set-alias-for-git-log)
      * [Color setting](#color-setting)
      * [git status: display/hide untracked files](#git-status-displayhide-untracked-files)
   * [Usage](#usage)
      * [Check difference between local and remote](#check-difference-between-local-and-remote)
   * [Assist Tool](#assist-tool)
      * [gh-md-toc](#gh-md-toc)
      * [gitignore.io](#gitignoreio)

<!-- Added by: shota, at: Wed Dec 23 10:53:33 JST 2020 -->

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

## git status: display/hide untracked files
**Approach: config**  
Set config to hide untracked files.  
```
git config status.showuntrackedfiles no
```

Set config to display untracked files.  
```
git config --unset status.showuntrackedfiles
```

**Approach: option**  
Use option `-uno` to hide untracked files.  
```
git status -uno
```

Use option `-u` to display untracked files.  
```
git status -u
```

# Usage
## Check difference between local and remote
There are two major approaches.  

**fetch + diff**  
It'll show the detail information.  
```
git fetch origin
git diff origin/master
```

**git remote show**  
It can be done by just one command.  
To check status, see the end of line; `local out of date` or `up to date`.
```
git remote show origin
```
# Assist Tool
## gh-md-toc
gh-md-toc is for you if you want to generate TOC for README.md or GitHub's wiki page and don't want to install any additional software.  
https://github.com/ekalinin/github-markdown-toc  

## gitignore.io
Create useful .gitignore files for your project.  
https://www.toptal.com/developers/gitignore  

