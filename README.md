# vim_config
My vim configuration files.

## How to config local vim
  1. clone the repository to a local directory

```shell  
  git clone https://github.com/advsail/vim_config.git
```

  2. copy the .vim folder to local home folder

```shell
  cp -a ./vim_config/.vim ~/
```
## Vim version tested

'Ubuntu 16.04 and vim version 7.4.1689'

'CentOS 6.4 Final and vim version 7.4.629'

Both installed from distribution's software source.

## Markdown Highlighting

Use the following plugin for markdown highlighting.

https://github.com/gabrielelana/vim-markdown

I'm using Pathogen, so the command to enable this plugin is as below

```shell
$ cd ~/.vim/bundle
$ git clone https://github.com/gabrielelana/vim-markdown.git
$ cd vim-markdown
$ rm -rf .git
```

## Using Vim on Mac

If you directly clone this repo and put it in .vim folder on Mac.
Vim will wor fine except the `indentline` will not show up. This
is due to for the Vim originally installed with Mac, `conceal` feature
is not added into it. This can be checked by running `:echo has("conceal")`
in Vim and if you get return value of 0, then `conceal` is not included.

Another way is running the following command 

```shell
vim --version | grep conceal
```

If you see `-conceal` then `conceal` is not included.

One solution for the above issue is re-install Vim through brew.

The original Vim is in `/usr/bin` and if you run `brew install vim` you will
find a new Vim in `/usr/local/bin`. The newly installed Vim has `conceal` included.

Searching in `/usr/bin` is prior than `/usr/local/bin` so you need to do the following
the make searching in `/usr/local/bin` ahead of `/usr/bin`.

Create a `.bash_profile` under home directory. Put `PATH="/usr/local/bin:$PATH"` in it.
Then either source this `.bash_profile` or restart the terminal.

The Vim installed through brew will be launched and `indentlines` will show up.
