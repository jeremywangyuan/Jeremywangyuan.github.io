---
layout:     post
title:      iTerm2 + zsh = 打造自己的終端機
date:       2017-09-27 23:00:00
summary:    iTerm2 + zsh = 打造自己的終端機
categories: useful_things
thumbnail: iterm
tags:
---

# iTerm2 + zsh = 打造自己的終端機
---

這篇要來介紹如何在OS X上, 打造出自己喜歡的終端機, 雖然本身OS X的Terminal並不差, 但還是有點陽春不好看

### iTerm2

[iTerm2](https://www.iterm2.com/)是一個open source的terminal, 而優點很簡單的就是更方便 好看

下載後, 打開 iTerm, 就可以進入以下路徑 iterm --> preference --> profiles --> colors --> load 去更改成你喜歡的外觀了

### zsh

zsh是用來取代 BASH 的一種工具, zsh的優點有不少，詳細可以看[介紹文](http://josephj.com/entry.php?id=314), 打開Terminal輸入 

```
brew install zsh zsh-completions
```

完成下載安裝, 並確認是否安裝成功

```
zsh --version
```

安裝完後, 在將zsh設成default shell, 須先 `sudo vim /etc/shells` 在文件最後加上 `/usr/local/bin/zsh` 然後

```
chsh -s /usr/local/bin/zsh
```

否則會噴 `chsh: /usr/bin/zsh: non-standard shell` 的error

最後重開, 輸入

```
echo $SHELL
```

出現 `/bin/zsh/` 就是成功了

### Oh My zsh

[Oh My Zsh](http://ohmyz.sh/) 是一個用來管理 ZSH 設定檔的框架, 提供了很多的外掛和主題可以選擇

安裝

```
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

使用主題, 可以上網去找各種, 而我是用[powerline](https://github.com/jeremyFreeAgent/oh-my-zsh-powerline-theme)

安裝powerline主題

```=
$ git clone git://github.com/jeremyFreeAgent/oh-my-zsh-powerline-theme ~/.ohmyzsh-powerline
$ cd .ohmyzsh-powerline/
$ ./install_in_omz.sh
```

然後 

```
$ cd ~
$ vim .zshrc
```

將ZSH_THEME=”” 修改成 `ZSH_THEME=”powerline”`

安裝powerline字體

```
$ git clone git://github.com/powerline/fonts ~/.powerline_fonts
$ cd ~/.powerline_fonts
$ ./install.sh
```

然後到 `iTerm -> Preferences -> Profile -> Text` 大致上就大功告成了

### 其他

- 內建外掛 : [oh-my-zsh wiki](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins)

- 更多外掛 : [awesome-zsh-plugins](https://github.com/unixorn/awesome-zsh-plugins)

  e.g. Auto suggestions

  ```
  $ git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
  $ vim .zshrc
  ```

  將plugins=”” 修改成 `plugins=(zsh-autosuggestions)` 

- 客制Prompt : 修改 `vim .zshrc` 到裡面去客制 

  e.g. 

  ```
  POWERLINE_HIDE_HOST_NAME="true"
  POWERLINE_DISABLE_RPOMPT="true"
  POWERLINE_FULL_CURRENT_PATH="true"
  ```




