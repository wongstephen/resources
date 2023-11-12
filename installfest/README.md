# Installfest

## Summary

This is intended for OSX 

## IDE

[Visual Studio Code](https://code.visualstudio.com/Download)

To be able to launch VS Code from your terminal: open the Command Palette (⇧⌘P) and type 'shell command' to find the Shell Command: Install 'code' command in PATH.

## Xcode

Needed for homebrew and other scripts to work

```shell
# macOS ONLY
xcode-select --install
```

## Homebrew Package Manager

[Homebrew](https://brew.sh/)

installation script
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
``` 

Follow the instructions in the CLI to add homebrew to the path
```sh
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/deako/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

## Install Git

`brew install git`

Then configure name and email for commits

```sh
 git config --global user.name "Your Name"
 git config --global user.email "you@example.com"
```

### Git set default branch to `main`

`git config --global init.defaultBranch main`

## Install yarn

`brew install yarn`

## Install NVM

[NVM](https://github.com/nvm-sh/nvm)

Install the main application
```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
```

Install the latest version of node, lts, and 18
```sh
nvm install lts/hydrogen
nvm install --lts
nvm install node
```
### Generate SSH key

### Show current folder and branch in ~/.zsh

Copy the following code to ~/.zsh 

```sh
# Git function: https://stackoverflow.com/questions/59009508/how-to-only-show-current-folder-and-git-branch-and-for-home-in-zsh
# load version control information
autoload -Uz vcs_info
precmd() { vcs_info }

# format vcs_info variable
zstyle ':vcs_info:git:*' formats '- %F{green}%b%f'

# set up the prompt to include git branch and complete working directory
# zsh documentation: http://zsh.sourceforge.net/Doc/Release/Prompt-Expansion.html
setopt PROMPT_SUBST
NEWLINE=$'\n'
PROMPT='%B%F{blue}%~ ${vcs_info_msg_0_}%f%b${NEWLINE}$ '
# set VS code as default editor
export EDITOR='code --wait'
export VISUAL='code --wait'

```